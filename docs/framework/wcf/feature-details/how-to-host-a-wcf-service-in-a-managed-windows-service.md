---
title: 'Como: hospedar um serviço WCF em um serviço Windows gerenciado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
ms.openlocfilehash: c63b249cf16100f0b18d622fdecd7cd375df83d8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59297753"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-windows-service"></a>Como: hospedar um serviço WCF em um serviço Windows gerenciado

Este tópico descreve as etapas básicas necessárias para criar um serviço do Windows Communication Foundation (WCF) que é hospedado por um serviço do Windows. O cenário é habilitado pelo serviço Windows gerenciado opção que é um serviço WCF de longa execução hospedado fora do Internet Information Services (IIS) em um ambiente seguro que não é ativada de mensagem de hospedagem. O tempo de vida do serviço é controlado pelo sistema operacional. Essa opção de hospedagem está disponível em todas as versões do Windows.

Os serviços Windows podem ser gerenciados com o Microsoft.ManagementConsole.SnapIn no MMC (Console de Gerenciamento Microsoft) e podem ser configurados para início automático quando o sistema for inicializado. Essa opção de hospedagem consiste em registrar o domínio do aplicativo (AppDomain) que hospeda um serviço WCF como um serviço gerenciado do Windows, para que o tempo de vida do processo do serviço é controlado pelo serviço controle Manager (SCM) para os serviços do Windows.

O código do serviço inclui uma implementação de serviço do contrato do serviço, de uma classe do serviço Windows e de uma classe de instalador. A classe de implementação de serviço, `CalculatorService`, é um serviço WCF. O `CalculatorWindowsService` é um serviço Windows. Para qualificar-se como um serviço Windows, a classe herda de `ServiceBase` e implementa os métodos `OnStart` e `OnStop`. Em `OnStart`, um <xref:System.ServiceModel.ServiceHost> é criado para o tipo `CalculatorService` e é aberto. Em `OnStop`, o serviço é interrompido e descartado. O host também é responsável por fornecer um endereço básico ao host de serviço, que foi configurado nas configurações do aplicativo. A classe de instalador, que herda de <xref:System.Configuration.Install.Installer>, permite que o programa seja instalado como um serviço Windows pela ferramenta Installutil.exe.

## <a name="construct-the-service-and-provide-the-hosting-code"></a>Construir o serviço e fornecer o código de hospedagem

1. Criar um novo Visual Studio **aplicativo de Console** projeto chamado **serviço**.

2. Renomeie Program.cs como Service.cs.

3. Alterar o namespace para `Microsoft.ServiceModel.Samples`.

4. Adicione referências aos assemblies a seguir:

    - System.ServiceModel.dll

    - System.ServiceProcess.dll

    - System.Configuration.Install.dll

5. Adicione as instruções de uso a seguir a Service.cs.

     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]

6. Defina o contrato de serviço `ICalculator` como mostrado no código a seguir.

     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]

7. Implemente o contrato de serviço em uma classe chamada `CalculatorService` como mostrado no código a seguir.

     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]

8. Crie uma nova classe chamada `CalculatorWindowsService` que herda da classe <xref:System.ServiceProcess.ServiceBase>. Adicione uma variável local chamada `serviceHost` para fazer referência à instância <xref:System.ServiceModel.ServiceHost>. Defina o método `Main` que chama `ServiceBase.Run(new CalculatorWindowsService)`

     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]

9. Substitua o método <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> criando e abrindo uma nova instância <xref:System.ServiceModel.ServiceHost> como mostrado no código a seguir.

     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]

10. Substitua o método <xref:System.ServiceProcess.ServiceBase.OnStop%2A> fechando <xref:System.ServiceModel.ServiceHost> como mostrado no código a seguir.

     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]

11. Crie uma nova classe chamada `ProjectInstaller` que herda de <xref:System.Configuration.Install.Installer> e que é marcada com <xref:System.ComponentModel.RunInstallerAttribute> definido como `true`. Isso permite que o serviço Windows seja instalado pela ferramenta Installutil.exe.

     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]

12. Remova a classe `Service` que foi gerada quando você criou o projeto.

13. Adicione um arquivo de configuração de aplicativo ao projeto. Substitua o conteúdo do arquivo pelo XML de configuração a seguir.

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.serviceModel>    <services>
          <!-- This section is optional with the new configuration model
               introduced in .NET Framework 4. -->
          <service name="Microsoft.ServiceModel.Samples.CalculatorService"
                   behaviorConfiguration="CalculatorServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>
            <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->
            <endpoint address=""
                      binding="wsHttpBinding"
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
            <endpoint address="mex"
                      binding="mexHttpBinding"
                      contract="IMetadataExchange" />
          </service>
        </services>
        <behaviors>
          <serviceBehaviors>
            <behavior name="CalculatorServiceBehavior">
              <serviceMetadata httpGetEnabled="true"/>
              <serviceDebug includeExceptionDetailInFaults="False"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>
      </system.serviceModel>
    </configuration>
    ```

     Clique com botão direito do arquivo App. config na **Gerenciador de soluções** e selecione **propriedades**. Sob **Copy to Output Directory** selecionar **Copy if Newer**.

     Este exemplo especifica explicitamente pontos de extremidade no arquivo de configuração. Se você não adicionar nenhum ponto de extremidade ao serviço, o tempo de execução adicionará pontos de extremidade padrão para você. Neste exemplo, como o serviço tem <xref:System.ServiceModel.Description.ServiceMetadataBehavior> definido como `true`, seu serviço também possui metadados de publicação habilitados. Para obter mais informações sobre pontos de extremidade, associações e comportamentos padrão, confira [Configuração simplificada](../../../../docs/framework/wcf/simplified-configuration.md) e [Configuração simplificada para serviços WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).

## <a name="install-and-run-the-service"></a>Instalar e executar o serviço

1. Crie a solução para criar o executável `Service.exe`.

2. Abra o Prompt de comando do desenvolvedor para Visual Studio e navegue até o diretório do projeto. Tipo `installutil bin\service.exe` no prompt de comando para instalar o serviço do Windows.

     Digite `services.msc` no prompt de comando para acessar o SCM. O serviço Windows deve aparecer em Serviços como “WCFWindowsServiceSample”. O serviço do WCF só pode responder aos clientes se o serviço do Windows está em execução. Para iniciar o serviço, clique duas vezes no SCM e selecione "Iniciar" ou tipo **net start-WCFWindowsServiceSample** no prompt de comando.

3. Se você fizer alterações no serviço, interrompa-o primeiro e desinstale-o. Para parar o serviço, o serviço no SCM com o botão direito e selecione "Parar", ou **stop net do tipo WCFWindowsServiceSample** no prompt de comando. Observe que se você interromper o serviço Windows e executar um cliente, uma exceção <xref:System.ServiceModel.EndpointNotFoundException> ocorrerá quando o cliente tentar acessar o serviço. Para desinstalar o tipo de serviço do Windows **installutil /u bin\service.exe** no prompt de comando.

## <a name="example"></a>Exemplo

A seguir está uma listagem completa do código usado por este tópico:

[!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
[!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]

Como a opção de "auto-hospedagem", o ambiente de hospedagem de serviços Windows requer que algum código de hospedagem seja criado como parte do aplicativo. O serviço é implementado como um aplicativo de console e contém seu próprio código de hospedagem. Em outros ambientes de hospedagem, como o WAS (Serviço de Ativação de Processos do Windows), hospedado no IIS, não é necessário que os desenvolvedores criem código de hospedagem.

## <a name="see-also"></a>Consulte também

- [Configuração simplificada](../../../../docs/framework/wcf/simplified-configuration.md)
- [Hospedagem em um aplicativo gerenciado](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)
- [Hospedando serviços](../../../../docs/framework/wcf/hosting-services.md)
- [Recursos de hospedagem do Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=201276)