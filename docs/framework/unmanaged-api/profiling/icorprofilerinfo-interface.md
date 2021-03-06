---
title: Interface ICorProfilerInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo
helpviewer_keywords:
- ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: eb4e4ce0-06e7-4469-bbc4-edc2eb5da4b1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b979b5f4ee849b96cd29b6c8e2e6a8932e88c182
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59201709"
---
# <a name="icorprofilerinfo-interface"></a>Interface ICorProfilerInfo
Fornece métodos para uso por criadores de perfil de código para se comunicar com o common language runtime (CLR) para controlar o monitoramento de eventos e solicitar informações.  
  
> [!NOTE]
>  Cada método no `ICorProfilerInfo` interface retorna um HRESULT para indicar êxito ou falha. Consulte CORERROR para obter uma lista dos possíveis códigos de retorno.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descrição|  
|------------|-----------------|  
|[Método BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)|Inicializa suporte à depuração em processo. Este método é obsoleto no .NET Framework versão 2.0.|  
|[Método EndInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-endinprocdebugging-method.md)|Fecha uma sessão de depuração em processo. Este método é obsoleto no .NET Framework versão 2.0.|  
|[Método ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)|Força a coleta de lixo a ocorrer no tempo de execução.|  
|[Método GetAppDomainInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)|Obtém informações sobre o domínio de aplicativo especificado.|  
|[Método GetAssemblyInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getassemblyinfo-method.md)|Obtém informações sobre o assembly especificado.|  
|[Método GetClassFromObject](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromobject-method.md)|Obtém o `ClassID` de um<br /><br /> objeto, dado seu `ObjectID`.|  
|[Método GetClassFromToken](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)|Obtém a ID da classe, considerando o token de metadados. Este método é obsoleto no .NET Framework versão 2.0. Use o [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) método em vez disso.|  
|[Método GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)|Obtém o pai de módulo e o token de metadados para a classe especificada.|  
|[Método GetCodeInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)|Obtém a extensão do código nativo associado com a ID da função especificada. Esse método é obsoleto. Use o [ICorProfilerInfo2::GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) método em vez disso.|  
|[Método GetCurrentThreadID](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)|Obtém a ID do thread atual, se ele for um thread gerenciado.|  
|[Método GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)|Obtém as categorias de evento atual para o qual o criador de perfil deseja receber notificações de eventos do CLR.|  
|[Método GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)|Mapeia um ponteiro de instrução de código gerenciado para um `FunctionID`.|  
|[Método GetFunctionFromToken](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromtoken-method.md)|Obtém a ID de uma função. Este método é obsoleto no .NET Framework versão 2.0. Use o [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) método em vez disso.|  
|[Método GetFunctionInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)|Obtém a classe pai e os metadados de token para a função especificada.|  
|[Método GetHandleFromThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gethandlefromthread-method.md)|A ID de um thread é mapeado para um identificador de thread do Win32.|  
|[Método GetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbody-method.md)|Obtém um ponteiro para o corpo de um método no código do Microsoft intermediate language (MSIL), começando em seu cabeçalho.|  
|[Método GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)|Obtém uma interface que fornece um método para alocar memória para ser usada para alternar o corpo de um método no código MSIL.|  
|[Método GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)|Obtém um mapa de deslocamentos do MSIL para os deslocamentos nativos para o código contido na função especificada.|  
|[Método GetInprocInspectionInterface](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectioninterface-method.md)|Obtém um objeto que pode ser consultado para uma interface ICorDebugProcess. Este método é obsoleto no .NET Framework versão 2.0.|  
|[Método GetInprocInspectionIThisThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectionithisthread-method.md)|Obtém um objeto que pode ser consultado para a interface ICorDebugThread. Este método é obsoleto no .NET Framework versão 2.0.|  
|[Método GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)|Dado um ID de módulo, retorna o nome do arquivo do módulo e a ID do assembly do pai do módulo.|  
|[Método GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)|Obtém uma instância de interface de metadados que é mapeado para o módulo especificado.|  
|[Método GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md)|Obtém o tamanho de um objeto especificado.|  
|[Método GetThreadContext](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)|Obtém a identidade de contexto associada ao thread especificado no momento.|  
|[Método GetThreadInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadinfo-method.md)|Obtém a atual identidade do thread Win32 do thread especificado.|  
|[Método GetTokenAndMetadataFromFunction](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gettokenandmetadatafromfunction-method.md)|Obtém o token de metadados e uma instância da interface de metadados que pode ser usado com o token para a função especificada.|  
|[Método IsArrayClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)|Determina se a classe especificada é uma classe de matriz.|  
|[Método SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)|Especifica as funções implementada pelo criador de perfil a ser chamado no "enter", "Sair" e "chamada tail" ganchos de funções gerenciadas.|  
|[Método SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)|Define um valor que especifica os tipos de eventos para os quais o criador de perfil deseja receber notificação do CLR.|  
|[Método SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)|Especifica a função implementada pelo criador de perfil que será chamada para mapear `FunctionID` ganchos de entrada/saída de função de valores em valores alternativos que são passados para o criador de perfil.|  
|[Método SetFunctionReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionrejit-method.md)|Não implementado. Não use.|  
|[Método SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)|Substitui o corpo da função especificada no módulo especificado.|  
|[Método SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)|Especifica como os deslocamentos do MSIL de original da função especificada são mapeados para os novo deslocamentos do MSIL de modificação de criador de perfil da função.|  
  
## <a name="remarks"></a>Comentários  
 Um criador de perfil chama um método no `ICorProfilerInfo` interface para se comunicar com o CLR para controlar o monitoramento de eventos e solicitar informações.  
  
 Os métodos do `ICorProfilerInfo` interface são implementados pelo CLR usando o modelo de Threading livre. Cada método retorna um HRESULT para indicar êxito ou falha. Consulte CORERROR para obter uma lista dos possíveis códigos de retorno.  
  
 O CLR passa, por meio da implementação do criador de perfil [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md), um `ICorProfilerInfo` interface para cada criador de perfil de código durante a inicialização. Um criador de perfil de código, em seguida, pode chamar métodos do `ICorProfilerInfo` interface para obter informações sobre o código gerenciado que está sendo executada sob o controle do CLR.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte também

- [Interfaces de criação de perfil](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Interface ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
