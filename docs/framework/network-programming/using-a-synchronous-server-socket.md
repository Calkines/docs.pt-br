---
title: Usando um soquete de servidor síncrono
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- synchronous server sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- Socket class, synchronous server sockets
- protocols, sockets
- sockets, synchronous server sockets
- Internet, sockets
ms.assetid: d1ce882e-653e-41f5-9289-844ec855b804
ms.openlocfilehash: 43e1d54d4e74b49fdf1a8997d1cc89492c9412bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117242"
---
# <a name="using-a-synchronous-server-socket"></a>Usando um soquete de servidor síncrono
Os soquetes de servidor síncrono suspendem a execução do aplicativo até que uma solicitação de conexão seja recebida no soquete. Os soquetes de servidor síncrono não são adequados para aplicativos que fazem uso intenso da rede em sua operação, mas podem ser adequados para aplicativos de rede simples.  
  
 Depois que um <xref:System.Net.Sockets.Socket> for definido para escutar em um ponto de extremidade usando os métodos <xref:System.Net.Sockets.Socket.Bind%2A> e <xref:System.Net.Sockets.Socket.Listen%2A>, ele estará pronto para aceitar solicitações de conexão de entrada usando o método <xref:System.Net.Sockets.Socket.Accept%2A>. O aplicativo é suspenso até que uma solicitação de conexão seja recebida quando o método **Accept** é chamado.  
  
 Quando uma solicitação de conexão é recebida, **Accept** retorna uma nova instância de **Socket** associada ao cliente que se conecta. O exemplo a seguir lê os dados do cliente, exibe-os no console e retorna os dados ao cliente. O **Socket** não especifica nenhum protocolo de mensagens e, portanto, a cadeia de caracteres “\<EOF>” marca o fim dos dados da mensagem. Ele supõe que um **Socket** chamado `listener` foi inicializado e associado a um ponto de extremidade.  
  
```vb  
Console.WriteLine("Waiting for a connection...")  
Dim handler As Socket = listener.Accept()  
Dim data As String = Nothing  
  
While True  
    bytes = New Byte(1024) {}  
    Dim bytesRec As Integer = handler.Receive(bytes)  
    data += Encoding.ASCII.GetString(bytes, 0, bytesRec)  
    If data.IndexOf("<EOF>") > - 1 Then  
        Exit While  
    End If  
End While  
  
Console.WriteLine("Text received : {0}", data)  
  
Dim msg As Byte() = Encoding.ASCII.GetBytes(data)  
handler.Send(msg)  
handler.Shutdown(SocketShutdown.Both)  
handler.Close()  
```  
  
```csharp  
Console.WriteLine("Waiting for a connection...");  
Socket handler = listener.Accept();  
String data = null;  
  
while (true) {  
    bytes = new byte[1024];  
    int bytesRec = handler.Receive(bytes);  
    data += Encoding.ASCII.GetString(bytes,0,bytesRec);  
    if (data.IndexOf("<EOF>") > -1) {  
        break;  
    }  
}  
  
Console.WriteLine( "Text received : {0}", data);  
  
byte[] msg = Encoding.ASCII.GetBytes(data);  
handler.Send(msg);  
handler.Shutdown(SocketShutdown.Both);  
handler.Close();  
```  
  
## <a name="see-also"></a>Consulte também

- [Usando um soquete de servidor assíncrono](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)
- [Exemplo de soquete de servidor síncrono](../../../docs/framework/network-programming/synchronous-server-socket-example.md)
- [Escutando com soquetes](../../../docs/framework/network-programming/listening-with-sockets.md)
