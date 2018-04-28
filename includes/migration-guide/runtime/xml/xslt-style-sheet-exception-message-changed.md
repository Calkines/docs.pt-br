### <a name="xslt-style-sheet-exception-message-changed"></a><span data-ttu-id="d6b7a-101">Mensagem de exceção da folha de estilos XSLT alterada</span><span class="sxs-lookup"><span data-stu-id="d6b7a-101">XSLT style sheet exception message changed</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d6b7a-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d6b7a-102">Details</span></span>|<span data-ttu-id="d6b7a-103">No .NET Framework 4.5, o texto da mensagem de erro quando um arquivo XSLT é muito complexo é &quot;A folha de estilos é muito complexa&quot;. Nas versões anteriores, a mensagem de erro era &quot;Erro de compilação de XSLT&quot;. O código do aplicativo que depende do texto da mensagem de erro não funcionará.</span><span class="sxs-lookup"><span data-stu-id="d6b7a-103">In the .NET Framework 4.5, the text of the error message when an XSLT file is too complex is &quot;The style sheet is too complex.&quot; In previous versions, the error message was &quot;XSLT compile error.&quot; Application code that depends on the text of the error message will no longer work.</span></span> <span data-ttu-id="d6b7a-104">No entanto, os tipos de exceção permanecem os mesmos, de modo que essa modificação não deve ter um impacto real.</span><span class="sxs-lookup"><span data-stu-id="d6b7a-104">However, the exception types remain the same, so this change should have no real impact.</span></span>|
|<span data-ttu-id="d6b7a-105">Sugestão</span><span class="sxs-lookup"><span data-stu-id="d6b7a-105">Suggestion</span></span>|<span data-ttu-id="d6b7a-106">Atualize qualquer código de aplicativo, dependendo da mensagem de exceção dessa condição de erro, para esperar a nova mensagem ou (ainda melhor) atualize o código para depender somente do tipo de exceção (<xref:System.Xml.Xsl.XsltException?displayProperty=name>), que não foi alterado.</span><span class="sxs-lookup"><span data-stu-id="d6b7a-106">Update any app code depending on the exception message from this error condition to expect the new message, or (even better) update the code to depend only on the exception type (<xref:System.Xml.Xsl.XsltException?displayProperty=name>), which has not changed.</span></span>|
|<span data-ttu-id="d6b7a-107">Escopo</span><span class="sxs-lookup"><span data-stu-id="d6b7a-107">Scope</span></span>|<span data-ttu-id="d6b7a-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d6b7a-108">Edge</span></span>|
|<span data-ttu-id="d6b7a-109">Versão</span><span class="sxs-lookup"><span data-stu-id="d6b7a-109">Version</span></span>|<span data-ttu-id="d6b7a-110">4.5</span><span class="sxs-lookup"><span data-stu-id="d6b7a-110">4.5</span></span>|
|<span data-ttu-id="d6b7a-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="d6b7a-111">Type</span></span>|<span data-ttu-id="d6b7a-112">Tempo de execução</span><span class="sxs-lookup"><span data-stu-id="d6b7a-112">Runtime</span></span>|
|<span data-ttu-id="d6b7a-113">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="d6b7a-113">Affected APIs</span></span>|<ul><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li></ul>|
