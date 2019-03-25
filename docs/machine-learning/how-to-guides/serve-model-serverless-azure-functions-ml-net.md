---
title: Implantar um modelo ML.NET ao Azure Functions
description: Usar um modelo de machine learning para Análise de Sentimento com o ML.NET para previsão pela internet usando o Azure Functions
ms.date: 03/08/2019
ms.custom: mvc,how-to
ms.openlocfilehash: db29e37660665b02ab93a07b37418f0c4c20a608
ms.sourcegitcommit: 5d9f4b805787f890ca6e0dc7ea30a43018bc9cbb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2019
ms.locfileid: "57788633"
---
# <a name="how-to-use-mlnet-model-in-azure-functions"></a><span data-ttu-id="e9ec3-103">Como fazer: Usar o modelo ML.NET no Azure Functions</span><span class="sxs-lookup"><span data-stu-id="e9ec3-103">How-To: Use ML.NET Model in Azure Functions</span></span>

<span data-ttu-id="e9ec3-104">Estas instruções mostram como previsões individuais podem ser feitas usando um modelo de machine learning com ML.NET, previamente criado, pela internet em um ambiente sem servidor como o Azure Functions.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-104">This how-to shows how individual predictions can be made using a pre-built ML.NET machine learning model through the internet in a serverless environment such as Azure Functions.</span></span>

> [!NOTE]
> <span data-ttu-id="e9ec3-105">Este tópico se refere ao ML.NET, que está atualmente na Versão Prévia, e o material pode estar sujeito a alterações.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-105">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="e9ec3-106">Para obter mais informações, visite [a introdução ao ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="e9ec3-106">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="e9ec3-107">Esta instrução e a amostra relacionada estão usando o **ML.NET versão 0.10** no momento.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-107">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="e9ec3-108">Saiba mais nas notas de versão no [repositório do github dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="e9ec3-108">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e9ec3-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e9ec3-109">Prerequisites</span></span>

- <span data-ttu-id="e9ec3-110">[Visual Studio 2017 15.6 ou posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) com a carga de trabalho "Desenvolvimento de plataforma cruzada do .NET Core" e “desenvolvimento do Azure” instalados.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-110">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span> 
- [<span data-ttu-id="e9ec3-111">Ferramentas do Azure Functions</span><span class="sxs-lookup"><span data-stu-id="e9ec3-111">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="e9ec3-112">Powershell</span><span class="sxs-lookup"><span data-stu-id="e9ec3-112">Powershell</span></span>
- <span data-ttu-id="e9ec3-113">Modelo previamente treinado.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-113">Pre-trained model.</span></span> 
    - <span data-ttu-id="e9ec3-114">Use o [tutorial de Análise de Sentimento com ML.NET](../tutorials/sentiment-analysis.md) para criar seu próprio modelo.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="e9ec3-115">Baixe este [modelo de machine learning previamente treinado para análise de sentimento](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="e9ec3-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="e9ec3-116">Criar um projeto no Azure Functions</span><span class="sxs-lookup"><span data-stu-id="e9ec3-116">Create Azure Functions Project</span></span>

1. <span data-ttu-id="e9ec3-117">Abra o Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="e9ec3-118">Selecione **Arquivo** > **Novo** > **Projeto** na barra de menus.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-118">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="e9ec3-119">Na caixa de diálogo **Novo projeto**, selecione o nó **Visual C#** seguido pelo nó **Nuvem**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-119">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="e9ec3-120">Em seguida, selecione o modelo de projeto do **Azure Functions**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-120">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="e9ec3-121">Na caixa de texto **Nome**, digite "SentimentAnalysisFunctionsApp" e, em seguida, selecione o botão **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-121">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="e9ec3-122">Na caixa de diálogo **Novo Projeto**, abra a lista suspensa acima das opções de projeto e selecione **Azure Functions v2 (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-122">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="e9ec3-123">Depois, selecione o projeto de **Gatilho de HTTP** e, em seguida, o botão **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-123">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="e9ec3-124">Crie um diretório chamado *MLModels* em seu projeto para salvar o modelo:</span><span class="sxs-lookup"><span data-stu-id="e9ec3-124">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="e9ec3-125">No **Gerenciador de Soluções**, clique com o botão direito do mouse no seu projeto e selecione **Adicionar** > **Nova Pasta**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-125">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="e9ec3-126">Digite "MLModels" e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-126">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="e9ec3-127">Instalar o **Pacote NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="e9ec3-127">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="e9ec3-128">No Gerenciador de Soluções, clique com o botão direito do mouse no seu projeto e selecione **Gerenciar Pacotes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-128">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="e9ec3-129">Escolha "nuget.org" como a Origem do pacote, selecione a guia Procurar, pesquise por **Microsoft.ML**, selecione o pacote na lista e escolha o botão **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-129">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="e9ec3-130">Selecione o botão **OK** na caixa de diálogo **Visualizar Alterações** e selecione o botão **Aceito** na caixa de diálogo **Aceitação da Licença**, se concordar com o termos de licença para os pacotes listados.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-130">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-built-model-to-project"></a><span data-ttu-id="e9ec3-131">Adicionar o modelo previamente criado ao projeto</span><span class="sxs-lookup"><span data-stu-id="e9ec3-131">Add Pre-built Model To Project</span></span>

1. <span data-ttu-id="e9ec3-132">Copie o modelo previamente criado para o diretório *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-132">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="e9ec3-133">No Gerenciador de Soluções, clique com o botão direito do mouse no arquivo do modelo criado previamente e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-133">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="e9ec3-134">Em **Avançado**, altere o valor de **Copiar para Diretório de Saída** para **Copiar se for mais novo**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-134">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-function-to-analyze-sentiment"></a><span data-ttu-id="e9ec3-135">Criar a função para analisar o sentimento</span><span class="sxs-lookup"><span data-stu-id="e9ec3-135">Create Function to Analyze Sentiment</span></span>

<span data-ttu-id="e9ec3-136">Crie uma classe para prever o sentimento.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-136">Create a class to predict sentiment.</span></span> <span data-ttu-id="e9ec3-137">Adicione uma nova classe ao seu projeto:</span><span class="sxs-lookup"><span data-stu-id="e9ec3-137">Add a new class to your project:</span></span>

1. <span data-ttu-id="e9ec3-138">No **Gerenciador de Soluções**, clique com o botão direito do mouse no projeto e selecione **Adicionar** > **Novo Item**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-138">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="e9ec3-139">Na caixa de diálogo **Adicionar novo item**, selecione **Função do Azure** e altere o campo **Nome** para *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-139">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="e9ec3-140">Em seguida, selecione o botão **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-140">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="e9ec3-141">Na caixa de diálogo **Nova Função do Azure**, selecione **Gatilho de HTTP**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-141">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="e9ec3-142">Depois, selecione o botão **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-142">Then, select the **OK** button.</span></span>

    <span data-ttu-id="e9ec3-143">O arquivo *AnalyzeSentiment.cs* é aberto no editor de códigos.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-143">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="e9ec3-144">Adicione a seguinte instrução `using` acima de *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="e9ec3-144">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

```csharp
using System;
using System.IO;
using System.Threading.Tasks;
using Microsoft.AspNetCore.Mvc;
using Microsoft.Azure.WebJobs;
using Microsoft.Azure.WebJobs.Extensions.Http;
using Microsoft.AspNetCore.Http;
using Microsoft.Extensions.Logging;
using Newtonsoft.Json;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using Microsoft.ML.Data;
using MLNETServerless.DataModels;
```

### <a name="create-data-models"></a><span data-ttu-id="e9ec3-145">Criar modelo de dados</span><span class="sxs-lookup"><span data-stu-id="e9ec3-145">Create Data Models</span></span>

<span data-ttu-id="e9ec3-146">Você precisa criar algumas classes para os dados e previsões de entrada.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-146">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="e9ec3-147">Adicione uma nova classe ao seu projeto:</span><span class="sxs-lookup"><span data-stu-id="e9ec3-147">Add a new class to your project:</span></span>

1. <span data-ttu-id="e9ec3-148">Crie um diretório chamado *DataModels* em seu projeto para salvar os modelos de dados: No Gerenciador de Soluções, clique com o botão direito do mouse no projeto e selecione **Adicionar > Nova pasta**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-148">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="e9ec3-149">Digite "DataModels" e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-149">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="e9ec3-150">No Gerenciador de Soluções, clique com o botão direito do mouse no diretório *DataModels* e selecione **Adicionar > Novo Item**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-150">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="e9ec3-151">Na caixa de diálogo **Adicionar Novo Item**, selecione **Classe** e altere o campo **Nome** para *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-151">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="e9ec3-152">Em seguida, selecione o botão **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-152">Then, select the **Add** button.</span></span> <span data-ttu-id="e9ec3-153">O arquivo *SentimentData.cs* é aberto no editor de códigos.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-153">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="e9ec3-154">Adicione a seguinte instrução using na parte superior do *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="e9ec3-154">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="e9ec3-155">Remova a definição de classe existente e adicione o seguinte código ao arquivo SentimentData.cs:</span><span class="sxs-lookup"><span data-stu-id="e9ec3-155">Remove the existing class definition and add the following code to the SentimentData.cs file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }
}
```

4. <span data-ttu-id="e9ec3-156">No Gerenciador de Soluções, clique com o botão direito do mouse no diretório *DataModels* e selecione **Adicionar > Novo Item**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-156">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="e9ec3-157">Na caixa de diálogo **Adicionar Novo Item**, selecione **Classe** e altere o campo **Nome** para *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-157">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="e9ec3-158">Em seguida, selecione o botão **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-158">Then, select the **Add** button.</span></span> <span data-ttu-id="e9ec3-159">O arquivo *SentimentPrediction.cs* é aberto no editor de códigos.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-159">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="e9ec3-160">Adicione a seguinte instrução "using" na parte superior do *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="e9ec3-160">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="e9ec3-161">Remova a definição de classe existente e adicione o seguinte código ao arquivo *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="e9ec3-161">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

### <a name="add-prediction-logic"></a><span data-ttu-id="e9ec3-162">Adicionar lógica de previsão</span><span class="sxs-lookup"><span data-stu-id="e9ec3-162">Add Prediction Logic</span></span>

<span data-ttu-id="e9ec3-163">Substitua a implementação existente do método *Run* na classe *AnalyzeSentiment* pelo código a seguir:</span><span class="sxs-lookup"><span data-stu-id="e9ec3-163">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

```csharp
    public static async Task<IActionResult> Run(
        [HttpTrigger(AuthorizationLevel.Function,"post", Route = null)] HttpRequest req,
        ILogger log)
    {
        log.LogInformation("C# HTTP trigger function processed a request.");

        //Create Context
        MLContext mlContext = new MLContext();

        //Load Model
        using (var fs = File.OpenRead("MLModels/sentiment_model.zip"))
        {
            model = mlContext.Model.Load(fs);
        }

        //Parse HTTP Request Body
        string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
        SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);

        //Create Prediction Engine
        PredictionEngine<SentimentData, SentimentPrediction> predictionEngine = model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);

        //Make Prediction
        SentimentPrediction prediction = predictionEngine.Predict(data);

        //Convert prediction to string
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        //Return Prediction
        return (ActionResult)new OkObjectResult(isToxic);
    }
}
```

## <a name="test-locally"></a><span data-ttu-id="e9ec3-164">Testar localmente</span><span class="sxs-lookup"><span data-stu-id="e9ec3-164">Test Locally</span></span>

<span data-ttu-id="e9ec3-165">Agora que está tudo definido, é hora de testar o aplicativo:</span><span class="sxs-lookup"><span data-stu-id="e9ec3-165">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="e9ec3-166">Executar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="e9ec3-166">Run the application</span></span>
1. <span data-ttu-id="e9ec3-167">Abra o PowerShell e digite o seguinte código no prompt, em que PORT é a porta em que seu aplicativo está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-167">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="e9ec3-168">Normalmente, a porta é a 7071.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-168">Typically the port is 7071.</span></span> 

```powershell
Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="e9ec3-169">Se houver êxito, a saída deverá ser semelhante ao texto abaixo:</span><span class="sxs-lookup"><span data-stu-id="e9ec3-169">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="e9ec3-170">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="e9ec3-170">Congratulations!</span></span> <span data-ttu-id="e9ec3-171">Você usou com êxito o modelo para fazer previsões pela internet usando uma função do Azure.</span><span class="sxs-lookup"><span data-stu-id="e9ec3-171">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e9ec3-172">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e9ec3-172">Next Steps</span></span>

- [<span data-ttu-id="e9ec3-173">Implantar no Azure</span><span class="sxs-lookup"><span data-stu-id="e9ec3-173">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)