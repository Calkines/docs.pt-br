---
title: Factory do canal de configuração
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: 5bee4c7cc2c2e64c6e0d8d0ec2634f9500cd9d51
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975865"
---
# <a name="configuration-channel-factory"></a>Factory do canal de configuração
Este exemplo aborda o uso do <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>. O <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> permite o gerenciamento centralizado de configuração de cliente do WCF. Isso também pode ser útil em cenários em que a configuração é selecionada ou alterada depois que o tempo de carregamento de domínio do aplicativo.

## <a name="demonstrates"></a>Demonstra
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>

## <a name="discussion"></a>Discussão
 Este exemplo mostra como usar <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> para adicionar um arquivo de configuração específico para um aplicativo cliente, sem a necessidade de usar o arquivo de configuração de aplicativo padrão.

 O exemplo consiste em dois projetos. O primeiro projeto é um serviço simples que é executado para responder a mensagens recebidas dos clientes. O segundo projeto é um aplicativo cliente que cria dois <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> objetos usando um <xref:System.Configuration.ExeConfigurationFileMap> Test.config arquivo de configuração e os utiliza para se comunicar com o serviço. Ambos os clientes se comunicam com o serviço usando a configuração especificada em Test.config.

 O código a seguir adiciona um arquivo de configuração personalizada a um aplicativo cliente.

```csharp
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();
fileMap.ExeConfigFilename = "Test.config";
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);

ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));
ICalculatorChannel client1 = factory1.CreateChannel();
```

#### <a name="to-set-up-build-and-run-the-sample"></a>Para configurar, compilar, e executar o exemplo

1. Abra o Visual Studio 2012 com privilégios de administrador.

2. A solução ConfigurationChannelFactory (2 projetos) com o botão direito e, em seguida, selecione **propriedades**.

3. Na **propriedades comuns**, selecione **projeto de inicialização**e, em seguida, clique em **vários projetos de inicialização**.

4. Mover o **Service** do projeto para o início da lista, com o **ação 'Start'** e, em seguida, mova o **cliente** projeto depois do **serviço**projeto, também com o **a ação 'Start'**, portanto, o **cliente** projeto é executado após o **serviço** projeto.

5. Clique em **Okey**, em seguida, pressione F5 (ou CTRL + F5) para executar o exemplo.

> [!IMPORTANT]
>  Os exemplos podem já estar instalados no seu computador. Verifique o seguinte diretório (padrão) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e o Windows Workflow Foundation (WF) exemplos do .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos. Este exemplo está localizado no seguinte diretório.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
