---
title: ".NET Framework에서 사용되지 않는 형식 | Microsoft 문서"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework 4.5, obsolete types
- types, obsolete in .NET Framework 4.5
- obsolete types [.NET Framework]
ms.assetid: e636d024-0fac-45eb-b721-25a8c0ceca8f
caps.latest.revision: 41
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 01c66e2c291766ba00376261740906934f065855
ms.openlocfilehash: b7040d4c82c9434b2d24a579a93602660479ec59
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="obsolete-types-in-the-net-framework"></a>.NET Framework에서 사용되지 않는 형식
<a name="introduction"></a> 이 문서의 표에는 어셈블리에서 구성된 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 및 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에서 사용하지 않는 형식이 나열되어 있습니다. 사용하지 않는 형식과 각 어셈블리에서 권장되는 대체 형식의 목록을 보려면 다음 링크를 사용합니다. 이러한 형식은 사용되지 않으므로 해당 형식의 멤버도 모두 사용되지 않습니다. .NET Framework 클래스 라이브러리의 사용되지 않는 멤버에 대한 추가 목록은 [사용되지 않는 멤버](../../../docs/framework/whats-new/obsolete-members.md)를 참조하십시오.  
  
-   [시스템 어셈블리에서 사용되지 않는 형식](#obsolete_types_in_system_assemblies)  
  
    -   [mscorlib.dll](#mscorlib)  
  
    -   [System.Core.dll](#Core)  
  
    -   [System.Data.dll](#data)  
  
    -   [System.Data.OracleClient.dll](#oracleclient)  
  
    -   [System.Design.dll](#design)  
  
    -   [System.dll](#system)  
  
    -   [System.EnterpriseServices.dll](#enterpriseservices)  
  
    -   [System.Net.dll](#net)  
  
    -   [System.ServiceModel.dll](#servicemodel)  
  
    -   [System.Web.dll](#web)  
  
    -   [System.Web.Mobile.dll](#mobile)  
  
    -   [System.Workflow.Activities.dll](#workflow_activities)  
  
    -   [System.Workflow.ComponentModel.dll](#workflow_componentmodel)  
  
    -   [System.Workflow.Runtime.dll](#workflow_runtime)  
  
    -   [System.WorkflowServices.dll](#workflowservices)  
  
    -   [System.Xaml.dll](#xaml)  
  
    -   [System.Xml.dll](#xml)  
  
    -   [WindowsBase.dll](#WindowsBase)  
  
-   [Microsoft 어셈블리에서 사용되지 않는 형식](#obsolete_types_in_microsoft_assemblies)  
  
    -   [IEHost.dll 및 IEExec.exe](#IEHost)  
  
    -   [Microsoft.Build.Engine.dll](#Engine)  
  
    -   [Microsoft.JScript.dll](#jscript)  
  
    -   [Microsoft.VisualBasic.Compatibility.dll](#VBCompat)  
  
    -   [Microsoft.VisualBasic.Compatibility.Data.dll](#VBCompatData)  
  
    -   [Microsoft.VisualC.dll](#visualc)  
  
<a name="obsolete_types_in_system_assemblies"></a>   
## <a name="obsolete-types-in-system-assemblies"></a>시스템 어셈블리에서 사용되지 않는 형식  
 다음 표에서는 시스템 어셈블리에서 사용되지 않는 것으로 선언된 형식을 보여 줍니다. 이러한 어셈블리는 .NET Framework를 대상으로 하는 일반\-용도의 응용 프로그램 개발에 사용됩니다.  
  
<a name="mscorlib"></a>   
### <a name="assembly-mscorlibdll"></a>어셈블리: mscorlib.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.ExecutionEngineException?displayProperty=fullName>|이 형식은 이전에 런타임에서 지정되지 않은 심각한 오류를 나타냈습니다. 이 예외는 런타임에서 더 이상 발생하지 않으므로 이 형식은 사용되지 않습니다.|  
|<xref:System.Collections.CaseInsensitiveHashCodeProvider?displayProperty=fullName>|대신 <xref:System.StringComparer?displayProperty=fullName>를 사용하십시오.|  
|<xref:System.Collections.IHashCodeProvider?displayProperty=fullName>|대신 <xref:System.Collections.IEqualityComparer?displayProperty=fullName>를 사용하십시오.|  
|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=fullName>|<xref:System.Configuration.Assemblies.AssemblyHash> 클래스는 사용되지 않습니다.|  
|<xref:System.Diagnostics.Contracts.Internal.ContractHelper?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음 System.Runtime.CompilerServices 네임스페이스의 <xref:System.Runtime.CompilerServices.ContractHelper?displayProperty=fullName> 클래스를 대신 사용합니다.|  
|<xref:System.Reflection.Emit.UnmanagedMarshal?displayProperty=fullName>|대체 API 사용 가능: <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=fullName> 사용자 지정 특성을 대신 내보냅니다.|  
|<xref:System.Runtime.InteropServices.BIND_OPTS?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.BIND_OPTS?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.BINDPTR?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.BINDPTR?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.CALLCONV?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.CALLCONV?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.CONNECTDATA?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.CONNECTDATA?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.DESCKIND?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.DESCKIND?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.DISPPARAMS?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.DISPPARAMS?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.ELEMDESC?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.ELEMDESC?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.EXCEPINFO?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.EXCEPINFO?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.FILETIME?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.FILETIME?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.FUNCDESC?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.FUNCDESC?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.FUNCFLAGS?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.FUNCFLAGS?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.FUNCKIND?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.FUNCKIND?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.IDispatchImplAttribute?displayProperty=fullName>|이 특성은 사용되지 않으며 이후 버전에서 제거됩니다.|  
|<xref:System.Runtime.InteropServices.IDispatchImplType?displayProperty=fullName>|<xref:System.Runtime.InteropServices.IDispatchImplAttribute?displayProperty=fullName>는 사용되지 않습니다.|  
|<xref:System.Runtime.InteropServices.IDLDESC?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.IDLDESC?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.IDLFLAG?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.IDLFLAG?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.IMPLTYPEFLAGS?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.IMPLTYPEFLAGS?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.INVOKEKIND?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.INVOKEKIND?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.LIBFLAGS?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.LIBFLAGS?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.PARAMDESC?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.PARAMDESC?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.PARAMFLAG?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.PARAMFLAG?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.SetWin32ContextInIDispatchAttribute?displayProperty=fullName>|이 특성은 사용되지 않습니다. 응용 프로그램 도메인에서는 더 이상 IDispatch 호출의 활성화 컨텍스트 경계를 따르지 않습니다.|  
|<xref:System.Runtime.InteropServices.STATSTG?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.STATSTG?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.SYSKIND?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.SYSKIND?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.TYPEATTR?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.TYPEATTR?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.TYPEDESC?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.TYPEDESC?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.TYPEFLAGS?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.TYPEFLAGS?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.TYPEKIND?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.TYPEKIND?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.TYPELIBATTR?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.TYPELIBATTR?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.UCOMIBindCtx?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.IBindCtx?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.UCOMIConnectionPoint?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.UCOMIConnectionPointContainer?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.UCOMIEnumConnectionPoints?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.IEnumConnectionPoints?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.UCOMIEnumConnections?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.IEnumConnections?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.UCOMIEnumMoniker?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.IEnumMoniker?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.UCOMIEnumString?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.IEnumString?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.UCOMIEnumVARIANT?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.UCOMIMoniker?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.IMoniker?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.UCOMIPersistFile?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.IPersistFile?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.UCOMIRunningObjectTable?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.IRunningObjectTable?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.UCOMIStream?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.UCOMITypeComp?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.ITypeComp?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.UCOMITypeInfo?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.UCOMITypeLib?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.ITypeLib?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.VARDESC?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.VARDESC?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Runtime.InteropServices.VARFLAGS?displayProperty=fullName>|대신 <xref:System.Runtime.InteropServices.ComTypes.VARFLAGS?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Security.SecurityCriticalScope?displayProperty=fullName>|<xref:System.Security.SecurityCriticalScope>는 .NET 2.0 투명도 호환성을 위한 용도로만 사용됩니다.|  
|<xref:System.Security.SecurityTreatAsSafeAttribute?displayProperty=fullName>|<xref:System.Security.SecurityTreatAsSafeAttribute>는 .NET 2.0 투명도 호환성을 위한 용도로만 사용됩니다. 대신 <xref:System.Security.SecuritySafeCriticalAttribute?displayProperty=fullName>를 사용하십시오.|  
|<xref:System.Security.Policy.FirstMatchCodeGroup?displayProperty=fullName>|이 형식은 사용되지 않으며 .NET Framework의 이후 릴리스에서 제거됩니다.|  
|<xref:System.Security.Policy.PermissionRequestEvidence?displayProperty=fullName>|어셈블리 수준의 선언적 보안은 사용되지 않으며 더 이상 기본적으로 CLR에서 적용되지 않습니다.|  
|<xref:System.Security.Policy.UnionCodeGroup?displayProperty=fullName>|이 형식은 사용되지 않으며 .NET Framework의 이후 릴리스에서 제거됩니다.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="Core"></a>   
### <a name="assembly-systemcoredll"></a>어셈블리: System.Core.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.Runtime.CompilerServices.ExecutionScope?displayProperty=fullName>|이 형식을 사용하면 컴파일러 오류가 생성됩니다.<br /><br /> 이 형식은 사용하지 마십시오.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="data"></a>   
### <a name="assembly-systemdatadll"></a>어셈블리: System.Data.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.Data.DataSysDescriptionAttribute?displayProperty=fullName>|<xref:System.Data.DataSysDescriptionAttribute>는 사용되지 않습니다.|  
|<xref:System.Data.PropertyAttributes?displayProperty=fullName>|<xref:System.Data.PropertyAttributes>는 사용되지 않습니다.|  
|<xref:System.Data.TypedDataSetGenerator?displayProperty=fullName>|<xref:System.Data.TypedDataSetGenerator> 클래스는 이후 릴리스에서 제거됩니다. System.Design.dll의 <xref:System.Data.Design.TypedDataSetGenerator?displayProperty=fullName>를 사용하십시오.|  
|<xref:System.Xml.XmlDataDocument?displayProperty=fullName>|<xref:System.Xml.XmlDataDocument> 클래스는 이후 릴리스에서 제거됩니다.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="oracleclient"></a>   
### <a name="assembly-systemdataoracleclientdll"></a>어셈블리: System.Data.OracleClient.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.Data.OracleClient.OracleClientFactory?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleClientFactory>는 사용되지 않습니다.|  
|<xref:System.Data.OracleClient.OracleCommand?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleCommand>는 사용되지 않습니다.|  
|<xref:System.Data.OracleClient.OracleCommandBuilder?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleCommandBuilder>는 사용되지 않습니다.|  
|<xref:System.Data.OracleClient.OracleConnection?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleConnection>는 사용되지 않습니다.|  
|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder>는 사용되지 않습니다.|  
|<xref:System.Data.OracleClient.OracleDataAdapter?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleDataAdapter>는 사용되지 않습니다.|  
|<xref:System.Data.OracleClient.OraclePermission?displayProperty=fullName>|<xref:System.Data.OracleClient.OraclePermission>는 사용되지 않습니다.|  
|<xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=fullName>|<xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=fullName>는 사용되지 않습니다.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="design"></a>   
### <a name="assembly-systemdesigndll"></a>어셈블리: System.Design.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.ComponentModel.Design.LocalizationExtenderProvider?displayProperty=fullName>|이 클래스는 사용되지 않습니다. 대신 <xref:System.ComponentModel.Design.Serialization.CodeDomLocalizationProvider?displayProperty=fullName> 를 사용하세요.|  
|<xref:System.Web.UI.Design.DataBindingCollectionConverter?displayProperty=fullName>|DataBindings 편집은 속성 표가 아닌 <xref:System.ComponentModel.Design.DesignerActionList?displayProperty=fullName>를 통해 시작되므로 이 형식은 사용하지 않는 것이 좋습니다.|  
|<xref:System.Web.UI.Design.DataBindingCollectionEditor?displayProperty=fullName>|DataBindings 편집은 속성 표가 아닌 <xref:System.ComponentModel.Design.DesignerActionList?displayProperty=fullName>를 통해 시작되므로 이 형식은 사용하지 않는 것이 좋습니다.|  
|<xref:System.Web.UI.Design.IControlDesignerBehavior?displayProperty=fullName>|<xref:System.Web.UI.Design.IControlDesignerTag?displayProperty=fullName> 및 <xref:System.Web.UI.Design.IControlDesignerView?displayProperty=fullName>를 대신 사용하는 것이 좋습니다.|  
|<xref:System.Web.UI.Design.IHtmlControlDesignerBehavior?displayProperty=fullName>|<xref:System.Web.UI.Design.IControlDesignerTag?displayProperty=fullName> 및 <xref:System.Web.UI.Design.IControlDesignerView?displayProperty=fullName>를 대신 사용하는 것이 좋습니다.|  
|<xref:System.Web.UI.Design.ITemplateEditingFrame?displayProperty=fullName>|템플릿 편집은 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>에서 처리되므로 이 형식은 사용하지 않는 것이 좋습니다. 템플릿 편집을 지원하려면 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=fullName> 속성에서 템플릿 데이터를 노출하고 <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=fullName>를 호출하십시오.|  
|<xref:System.Web.UI.Design.IWebFormReferenceManager?displayProperty=fullName>|<xref:System.Web.UI.Design.WebFormsReferenceManager?displayProperty=fullName>를 대신 사용하는 것이 좋습니다. <xref:System.Web.UI.Design.WebFormsReferenceManager>는 기능을 추가로 포함하며 보다 높은 확장성을 허용합니다. <xref:System.Web.UI.Design.WebFormsReferenceManager>를 가져오려면 `RootDesigner.ReferenceManager`의 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName> 속성을 사용하십시오.|  
|<xref:System.Web.UI.Design.IWebFormsDocumentService?displayProperty=fullName>|<xref:System.Web.UI.Design.WebFormsRootDesigner?displayProperty=fullName>를 대신 사용하는 것이 좋습니다. <xref:System.Web.UI.Design.WebFormsRootDesigner>는 기능을 추가로 포함하며 보다 높은 확장성을 허용합니다. <xref:System.Web.UI.Design.WebFormsRootDesigner>를 가져오려면 <xref:System.Web.UI.Design.ControlDesigner.RootDesigner%2A>의 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName> 속성을 사용하십시오.|  
|<xref:System.Web.UI.Design.ITemplateEditingService?displayProperty=fullName>|템플릿 편집은 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>에서 처리되므로 이 형식은 사용하지 않는 것이 좋습니다. 템플릿 편집을 지원하려면 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=fullName> 속성에서 템플릿 데이터를 노출하고 <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=fullName>를 호출하십시오.|  
|<xref:System.Web.UI.Design.ReadWriteControlDesigner?displayProperty=fullName>|콘텐츠 편집에 <xref:System.Web.UI.Design.ContainerControlDesigner?displayProperty=fullName>을 사용하는 <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=fullName>를 대신 사용하는 것이 좋습니다. 디자이너 영역을 사용하면 편집 중인 콘텐츠를 보다 효율적으로 제어할 수 있습니다.|  
|<xref:System.Web.UI.Design.TemplateEditingService?displayProperty=fullName>|템플릿 편집은 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>에서 처리되므로 이 형식은 사용하지 않는 것이 좋습니다. 템플릿 편집을 지원하려면 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=fullName> 속성에서 템플릿 데이터를 노출하고 <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=fullName>를 호출하십시오.|  
|<xref:System.Web.UI.Design.TemplateEditingVerb?displayProperty=fullName>|템플릿 편집은 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>에서 처리되므로 이 형식은 사용하지 않는 것이 좋습니다. 템플릿 편집을 지원하려면 <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=fullName> 속성에서 템플릿 데이터를 노출하고 <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=fullName>를 호출하십시오.|  
|<xref:System.Web.UI.Design.WebControls.CalendarAutoFormatDialog?displayProperty=fullName>|자동 서식 대화 상자는 디자이너 호스트를 통해 시작되므로 이 형식은 사용하지 않는 것이 좋습니다. 사용 가능한 자동 서식 목록은 <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName> 속성의 <xref:System.Web.UI.Design.ControlDesigner.AutoFormats%2A?displayProperty=fullName>에서 노출됩니다.|  
|<xref:System.Web.UI.Design.WebControls.PanelDesigner?displayProperty=fullName>|콘텐츠 편집에 <xref:System.Web.UI.Design.WebControls.PanelContainerDesigner?displayProperty=fullName>을 사용하는 <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=fullName>를 대신 사용하는 것이 좋습니다. 디자이너 영역을 사용하면 편집 중인 콘텐츠를 보다 효율적으로 제어할 수 있습니다.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="system"></a>   
### <a name="assembly-systemdll"></a>어셈블리: System.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.ComponentModel.IComNativeDescriptorHandler?displayProperty=fullName>|이 인터페이스는 사용되지 않습니다. <xref:System.ComponentModel.TypeDescriptionProvider?displayProperty=fullName> 형식을 처리하려면 대신 <xref:System.ComponentModel.TypeDescriptor.ComObjectType%2A?displayProperty=fullName>를 추가합니다.|  
|<xref:System.ComponentModel.RecommendedAsConfigurableAttribute?displayProperty=fullName>|새 설정 모델을 사용하려면 대신 <xref:System.ComponentModel.SettingsBindableAttribute?displayProperty=fullName>를 사용하십시오.|  
|<xref:System.ComponentModel.Design.Serialization.RootDesignerSerializerAttribute?displayProperty=fullName>|이 특성은 사용되지 않습니다. 대신 <xref:System.ComponentModel.Design.Serialization.DesignerSerializerAttribute?displayProperty=fullName>를 사용하세요. 예를 들어 CodeDom에 대해 루트 디자이너를 지정하려면 `DesignerSerializerAttribute\(...,typeof\(TypeCodeDomSerializer\)\)`를 사용하십시오.|  
|<xref:System.Diagnostics.DiagnosticsConfigurationHandler?displayProperty=fullName>|이 클래스는 사용되지 않습니다.|  
|<xref:System.Diagnostics.PerformanceCounterManager?displayProperty=fullName>|이 클래스는 사용되지 않습니다. 대신 <xref:System.Diagnostics.PerformanceCounter?displayProperty=fullName> 클래스를 통해 성능 카운터를 사용하십시오.|  
|<xref:System.Net.GlobalProxySelection?displayProperty=fullName>|이 클래스는 사용되지 않습니다. 전역 기본 프록시를 액세스 및 설정하려면 대신 <xref:System.Net.WebRequest.DefaultWebProxy%2A?displayProperty=fullName>를 사용하십시오. <xref:System.Net.GlobalProxySelection.GetEmptyWebProxy%2A?displayProperty=fullName> 대신 'null'을 사용하십시오.|  
|<xref:System.Net.Sockets.SocketClientAccessPolicyProtocol?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 이 형식을 사용하면 컴파일러 오류가 생성됩니다.<br /><br /> 이 API는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="enterpriseservices"></a>   
### <a name="assembly-systementerpriseservicesdll"></a>어셈블리: System.EnterpriseServices.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.EnterpriseServices.RegistrationHelperTx?displayProperty=fullName>|<xref:System.EnterpriseServices.RegistrationHelperTx> 클래스는 사용되지 않습니다.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="net"></a>   
### <a name="assembly-systemnetdll"></a>어셈블리: System.Net.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.Net.INetworkProgress?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 이 형식을 사용하면 컴파일러 오류가 생성됩니다.<br /><br /> 이 API는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.|  
|<xref:System.Net.IUnsafeWebRequestCreate?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 이 형식을 사용하면 컴파일러 오류가 생성됩니다.<br /><br /> 이 API는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.|  
|<xref:System.Net.NetworkProgressChangedEventArgs?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 이 형식을 사용하면 컴파일러 오류가 생성됩니다.<br /><br /> 이 API는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.|  
|<xref:System.Net.UiSynchronizationContext?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 이 형식을 사용하면 컴파일러 오류가 생성됩니다.<br /><br /> 이 API는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.|  
|<xref:System.Net.Sockets.HttpPolicyDownloaderProtocol?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 이 형식을 사용하면 컴파일러 오류가 생성됩니다.<br /><br /> 이 API는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.|  
|<xref:System.Net.Sockets.SecurityCriticalAction?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 이 형식을 사용하면 컴파일러 오류가 생성됩니다.<br /><br /> 이 API는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.|  
|<xref:System.Net.Sockets.SocketPolicy?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 이 형식을 사용하면 컴파일러 오류가 생성됩니다.<br /><br /> 이 API는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.|  
|<xref:System.Net.Sockets.UdpAnySourceMulticastClient?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 이 형식을 사용하면 컴파일러 오류가 생성됩니다.<br /><br /> 이 API는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.|  
|<xref:System.Net.Sockets.UdpSingleSourceMulticastClient?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 이 형식을 사용하면 컴파일러 오류가 생성됩니다.<br /><br /> 이 API는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="servicemodel"></a>   
### <a name="assembly-systemservicemodeldll"></a>어셈블리: System.ServiceModel.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.ServiceModel.NetPeerTcpBinding?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 피어 채널 기능은 사용되지 않으며 향후 제거될 예정입니다.|  
|<xref:System.ServiceModel.Channels.HttpCookieContainerBindingElement?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 이 형식은 사용되지 않습니다. Http <xref:System.Net.CookieContainer>를 사용하려면 Http 바인딩 또는 `AllowCookies`의 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> 속성을 사용합니다.|  
|<xref:System.ServiceModel.Channels.PeerCustomResolverBindingElement?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 피어 채널 기능은 사용되지 않으며 향후 제거될 예정입니다.|  
|<xref:System.ServiceModel.Channels.PeerTransportBindingElement?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 피어 채널 기능은 사용되지 않으며 향후 제거될 예정입니다.|  
|<xref:System.ServiceModel.Configuration.NetPeerTcpBindingCollectionElement?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 피어 채널 기능은 사용되지 않으며 향후 제거될 예정입니다.|  
|<xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 피어 채널 기능은 사용되지 않으며 향후 제거될 예정입니다.|  
|<xref:System.ServiceModel.Configuration.PeerTransportElement?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 피어 채널 기능은 사용되지 않으며 향후 제거될 예정입니다.|  
|<xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 피어 채널 기능은 사용되지 않으며 향후 제거될 예정입니다.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="web"></a>   
### <a name="assembly-systemwebdll"></a>어셈블리: System.Web.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.Web.Configuration.PassportAuthentication?displayProperty=fullName>|이 형식은 사용되지 않습니다. Passport 인증 제품은 더 이상 지원되지 않으며 [Microsoft Account](http://go.microsoft.com/fwlink/?LinkId=733413)로 대체되었습니다.|  
|<xref:System.Web.Mail.MailAttachment?displayProperty=fullName>|<xref:System.Net.Mail.Attachment?displayProperty=fullName>를 대신 사용하는 것이 좋습니다.|  
|<xref:System.Web.Mail.MailEncoding?displayProperty=fullName>|<xref:System.Net.Mime.TransferEncoding?displayProperty=fullName>를 대신 사용하는 것이 좋습니다.|  
|<xref:System.Web.Mail.MailFormat?displayProperty=fullName>|<xref:System.Net.Mail.MailMessage.IsBodyHtml%2A?displayProperty=fullName>를 대신 사용하는 것이 좋습니다.|  
|<xref:System.Web.Mail.MailMessage?displayProperty=fullName>|<xref:System.Net.Mail.MailMessage?displayProperty=fullName>를 대신 사용하는 것이 좋습니다.|  
|<xref:System.Web.Mail.MailPriority?displayProperty=fullName>|<xref:System.Net.Mail.MailPriority?displayProperty=fullName>를 대신 사용하는 것이 좋습니다.|  
|<xref:System.Web.Mail.SmtpMail?displayProperty=fullName>|<xref:System.Net.Mail.SmtpClient?displayProperty=fullName>를 대신 사용하는 것이 좋습니다.|  
|<xref:System.Web.Security.PassportAuthenticationEventArgs?displayProperty=fullName>|이 형식은 사용되지 않습니다. Passport 인증 제품은 더 이상 지원되지 않으며 [Microsoft Account](http://go.microsoft.com/fwlink/?LinkId=733413)로 대체되었습니다.|  
|<xref:System.Web.Security.PassportAuthenticationEventHandler?displayProperty=fullName>|이 형식은 사용되지 않습니다. Passport 인증 제품은 더 이상 지원되지 않으며 [Microsoft Account](http://go.microsoft.com/fwlink/?LinkId=733413)로 대체되었습니다.|  
|<xref:System.Web.Security.PassportAuthenticationModule?displayProperty=fullName>|이 형식은 사용되지 않습니다. Passport 인증 제품은 더 이상 지원되지 않으며 [Microsoft Account](http://go.microsoft.com/fwlink/?LinkId=733413)로 대체되었습니다.|  
|<xref:System.Web.Security.PassportIdentity?displayProperty=fullName>|이 형식은 사용되지 않습니다. Passport 인증 제품은 더 이상 지원되지 않으며 [Microsoft Account](http://go.microsoft.com/fwlink/?LinkId=733413)로 대체되었습니다.|  
|<xref:System.Web.Security.PassportPrincipal?displayProperty=fullName>|이 형식은 사용되지 않습니다. Passport 인증 제품은 더 이상 지원되지 않으며 [Microsoft Account](http://go.microsoft.com/fwlink/?LinkId=733413)로 대체되었습니다.|  
|<xref:System.Web.UI.ObjectConverter?displayProperty=fullName>|<xref:System.Convert?displayProperty=fullName> 및 <xref:System.String.Format%2A?displayProperty=fullName>를 대신 사용하는 것이 좋습니다.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="mobile"></a>   
### <a name="assembly-systemwebmobiledll"></a>어셈블리: System.Web.Mobile.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.Web.Mobile.CookielessData?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.Mobile.DeviceFilterElement?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.Mobile.DeviceFilterElementCollection?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.Mobile.DeviceFiltersSection?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.Mobile.ErrorHandlerModule?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.Mobile.MobileCapabilities?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.Mobile.MobileDeviceCapabilitiesSectionHandler?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.Mobile.MobileErrorInfo?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.Mobile.MobileFormsAuthentication?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.Design.MobileControls.IMobileDesigner?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.Design.MobileControls.IMobileWebFormServices?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.Design.MobileControls.MobileResource?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.Design.MobileControls.Converters.DataFieldConverter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.Design.MobileControls.Converters.DataMemberConverter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.AdRotator?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Alignment?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ArrayListCollectionBase?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.BaseValidator?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.BooleanOption?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Calendar?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Command?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.CommandFormat?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.CompareValidator?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Constants?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ControlElement?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ControlElementCollection?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ControlPager?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.CustomValidator?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.DesignerAdapterAttribute?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.DeviceElement?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.DeviceElementCollection?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.DeviceOverridableAttribute?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.DeviceSpecific?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoice?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceCollection?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceControlBuilder?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceTemplateBuilder?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceTemplateContainer?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificControlBuilder?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ErrorFormatterPage?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.FontInfo?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.FontSize?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Form?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.FormControlBuilder?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.FormMethod?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.IControlAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Image?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.IObjectListFieldCollection?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.IPageAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ItemPager?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ITemplateable?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Label?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Link?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.List?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ListCommandEventArgs?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ListCommandEventHandler?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ListControlBuilder?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ListDataBindEventArgs?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ListDataBindEventHandler?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ListDecoration?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ListSelectType?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.LiteralLink?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.LiteralText?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.LiteralTextContainerControlBuilder?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.LiteralTextControlBuilder?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.LoadItemsEventArgs?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.LoadItemsEventHandler?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.MobileControl?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.MobileControlBuilder?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.MobileControlsSection?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.MobileControlsSectionHandler?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.MobileListItem?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.MobileListItemCollection?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.MobileListItemType?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.MobilePage?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.MobileTypeNameConverter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.MobileUserControl?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectList?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListCommand?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListCommandCollection?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListCommandEventArgs?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListCommandEventHandler?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListControlBuilder?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListDataBindEventArgs?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListDataBindEventHandler?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListField?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListFieldCollection?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListItem?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListItemCollection?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListSelectEventArgs?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListSelectEventHandler?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListShowCommandsEventArgs?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListShowCommandsEventHandler?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListTitleAttribute?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ObjectListViewMode?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.PagedControl?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.PagerStyle?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Panel?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.PanelControlBuilder?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.PersistNameAttribute?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.PhoneCall?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.RangeValidator?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.RegularExpressionValidator?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.RequiredFieldValidator?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.SelectionList?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Style?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.StyleSheet?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.StyleSheetControlBuilder?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.TemplateContainer?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.TextBox?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.TextBoxControlBuilder?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.TextControl?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.TextView?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.TextViewElement?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.ValidationSummary?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Wrapping?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlCalendarAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlCommandAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlFormAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlImageAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlLinkAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlMobileTextWriter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlPageAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlPhoneCallAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlSelectionListAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlTextBoxAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.ControlAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlCalendarAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlCommandAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlControlAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlFormAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlImageAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLabelAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLinkAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlListAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLiteralTextAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlMobileTextWriter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlObjectListAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPageAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPanelAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPhoneCallAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlSelectionListAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlTextBoxAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlTextViewAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlValidationSummaryAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlValidatorAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.MobileTextWriter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.MultiPartWriter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.UpWmlMobileTextWriter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.UpWmlPageAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlCalendarAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlCommandAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlControlAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlFormAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlImageAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlLabelAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlLinkAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlListAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlLiteralTextAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlMobileTextWriter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlObjectListAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlPageAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlPanelAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlPhoneCallAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlPostFieldType?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlSelectionListAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlTextBoxAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlTextViewAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlValidationSummaryAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlValidatorAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.Doctype?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.StyleSheetLocation?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCalendarAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCommandAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlControlAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCssHandler?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlFormAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlImageAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLabelAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLinkAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlListAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLiteralTextAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlMobileTextWriter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlObjectListAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPageAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPanelAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPhoneCallAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlSelectionListAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlTextBoxAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlTextViewAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlValidationSummaryAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlValidatorAdapter?displayProperty=fullName>|System.Web.Mobile.dll 어셈블리는 사용되지 않으므로 사용하면 안 됩니다. ASP.NET 모바일 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [모바일용 ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231)을 참조하십시오.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="workflow_activities"></a>   
### <a name="assembly-systemworkflowactivitiesdll"></a>어셈블리: System.Workflow.Activities.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.Workflow.Activities?displayProperty=fullName> 네임스페이스의 모든 형식|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.Activities.Configuration.ActiveDirectoryRoleFactoryConfiguration?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.Activities.Rules.RuleActionTrackingEvent?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.Activities.Rules.RuleConditionReference?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.Activities.Rules.RuleSetReference?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="workflow_componentmodel"></a>   
### <a name="assembly-systemworkflowcomponentmodeldll"></a>어셈블리: System.Workflow.ComponentModel.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.Workflow.ComponentModel> 및 <xref:System.Workflow.ComponentModel.GetValueOverride?displayProperty=fullName>를 제외한 <xref:System.Workflow.ComponentModel.SetValueOverride?displayProperty=fullName> 네임스페이스의 모든 형식|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.ComponentModel.Compiler> 및 <xref:System.Workflow.ComponentModel.Compiler.ValidationError?displayProperty=fullName>를 제외한 <xref:System.Workflow.ComponentModel.Compiler.ValidationErrorCollection?displayProperty=fullName> 네임스페이스의 모든 형식|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.ComponentModel.Design>를 제외한 <xref:System.Workflow.ComponentModel.Design.ConnectorEventHandler> 네임스페이스의 모든 형식|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivityCodeDomSerializationManager?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivityCodeDomSerializer?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivityMarkupSerializer?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivitySurrogateSelector?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivityTypeCodeDomSerializer?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.ComponentModel.Serialization.CompositeActivityMarkupSerializer?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.ComponentModel.Serialization.DependencyObjectCodeDomSerializer?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="workflow_runtime"></a>   
### <a name="assembly-systemworkflowruntimedll"></a>어셈블리: System.Workflow.Runtime.dll  
  
|형식|메시지|  
|----------|-------------| 
|<xref:System.Activities.Statements.Interop>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br />Workflow Foundation 3.0 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 Workflow 4.0 형식을 사용하세요.|  
|<xref:System.Activities.Tracking.InteropTrackingRecord>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br />Workflow Foundation 3.0 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 Workflow 4.0 형식을 사용하세요.|   
|<xref:System.Workflow.Runtime> 네임스페이스의 모든 형식|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.Runtime.Configuration> 네임스페이스의 모든 형식|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.Runtime.DebugEngine>를 제외한 <xref:System.Workflow.Runtime.DebugEngine.DebugEngineCallback> 네임스페이스의 모든 형식|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.Runtime.Hosting>를 제외한 <xref:System.Workflow.Runtime.Hosting.WorkflowCommitWorkBatchService.CommitWorkBatchCallback> 네임스페이스의 모든 형식|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
|<xref:System.Workflow.Runtime.Tracking> 네임스페이스의 모든 형식|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> System.Workflow.\* 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 형식을 사용하세요.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="workflowservices"></a>   
### <a name="assembly-systemworkflowservicesdll"></a>어셈블리: System.WorkflowServices.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.ServiceModel.WorkflowServiceHost?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Activation.WorkflowServiceHostFactory?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Activities.Description.WorkflowRuntimeEndpoint?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Configuration.ExtendedWorkflowRuntimeServiceElementCollection?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Configuration.PersistenceProviderElement?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Configuration.WorkflowRuntimeElement?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Description.DurableOperationAttribute?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Description.DurableServiceAttribute?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Description.PersistenceProviderBehavior?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Description.UnknownExceptionAction?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Description.WorkflowRuntimeBehavior?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Dispatcher.DurableOperationContext?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Persistence.InstanceLockException?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Persistence.InstanceNotFoundException?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Persistence.LockingPersistenceProvider?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Persistence.PersistenceException?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Persistence.PersistenceProvider?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Persistence.PersistenceProviderFactory?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.ServiceModel.Persistence.SqlPersistenceProviderFactory?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.Workflow.Activities?displayProperty=fullName> 네임스페이스의 모든 형식|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
|<xref:System.Workflow.Runtime.Hosting.ChannelManagerService?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> WF 3 형식은 사용되지 않습니다. 대신 <xref:System.Activities>.\*의 새 WF 4 형식을 사용하세요.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="xaml"></a>   
### <a name="assembly-systemxamldll"></a>어셈블리: System.Xaml.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute?displayProperty=fullName>|XAML 파서에서 사용되지 않습니다. <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute?displayProperty=fullName>를 참조하십시오.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="xml"></a>   
### <a name="assembly-systemxmldll"></a>어셈블리: System.Xml.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.Xml.IApplicationResourceStreamResolver?displayProperty=fullName>|.NET Framework 4.5에서 처음으로 사용되지 않음<br /><br /> 이 형식을 사용하면 컴파일러 오류가 생성됩니다.<br /><br /> 이 API는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.|  
|<xref:System.Xml.Schema.XmlSchemaCollection?displayProperty=fullName>|스키마 컴파일 및 유효성 검사에는 <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=fullName>을 사용하십시오.|  
|<xref:System.Xml.XmlValidatingReader?displayProperty=fullName>|대신 적절한 <xref:System.Xml.XmlReader?displayProperty=fullName>를 사용하여 <xref:System.Xml.XmlReader.Create%2A?displayProperty=fullName> 메서드에서 만드는 <xref:System.Xml.XmlReaderSettings?displayProperty=fullName>를 사용하십시오.|  
|<xref:System.Xml.XmlXapResolver?displayProperty=fullName>|이 형식을 사용하면 컴파일러 오류가 생성됩니다. 이 API는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.|  
|<xref:System.Xml.Xsl.XslTransform?displayProperty=fullName>|이 클래스는 사용되지 않습니다. 대신 <xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=fullName>를 사용하십시오.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="WindowsBase"></a>   
### <a name="assembly-windowsbasedll"></a>어셈블리: WindowsBase.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:System.Windows.Markup.IReceiveMarkupExtension?displayProperty=fullName>|<xref:System.Windows.Markup.IReceiveMarkupExtension?displayProperty=fullName>는 사용되지 않습니다. 이 인터페이스는 더 이상 사용되지 않습니다.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="obsolete_types_in_microsoft_assemblies"></a>   
## <a name="obsolete-types-in-microsoft-assemblies"></a>Microsoft 어셈블리에서 사용되지 않는 형식  
 다음 단원에서는 Microsoft 어셈블리에서 사용되지 않는 형식을 보여 줍니다. 이러한 어셈블리는 Microsoft.JScript.dll, Microsoft.VisualC.dll 등의 개별 언어를 대상으로 하는 어셈블리와 같은 특수 용도의 어셈블리입니다.  
  
<a name="IEHost"></a>   
### <a name="assembly-iehostdll-and-ieexecexe"></a>어셈블리: IEHost.dll 및 IEExec.exe  
 IEHost.dll 및 IEExec.exe 어셈블리는 .NET Framework에서 제거되었습니다. 해당 형식 및 멤버는 모두 사용되지 않으며 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]의 일부로 지원되지 않습니다. 이러한 어셈블리는 Windows Forms 컨트롤을 호스팅하여 Internet Explorer에서 실행 파일을 실행하기 위해 사용되었습니다. ClickOnce, XBAP(XAML 브라우저 응용 프로그램) 및 Microsoft Silverlight를 대신 사용하는 것이 좋습니다.  
  
 [맨 위로 이동](#introduction)  
  
<a name="Engine"></a>   
### <a name="assembly-microsoftbuildenginedll"></a>어셈블리: Microsoft.Build.Engine.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:Microsoft.Build.BuildEngine.Engine?displayProperty=fullName>|이 클래스는 사용되지 않습니다. 대신 *Microsoft.Build* 어셈블리의 <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=fullName>을 사용하세요.|  
|<xref:Microsoft.Build.BuildEngine.Project?displayProperty=fullName>|이 클래스는 사용되지 않습니다. 대신 *Microsoft.Build* 어셈블리의 <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=fullName>을 사용하세요.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="jscript"></a>   
### <a name="assembly-microsoftjscriptdll"></a>어셈블리: Microsoft.JScript.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:Microsoft.JScript.Vsa.BaseVsaEngine?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.BaseVsaSite?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.BaseVsaStartup?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaCodeItem?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaEngine?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaError?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaGlobalItem?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaItem?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaItems?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaPersistSite?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaReferenceItem?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaSite?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.JSVsaError?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.JSVsaException?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.JSVsaItemFlag?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.JSVsaItemType?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.ResInfo?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
|<xref:Microsoft.JScript.Vsa.VsaEngine?displayProperty=fullName>|이 형식은 Visual Studio 2005에서 사용되지 않으므로 사용하지 않는 것이 좋습니다. 이 기능을 대체할 기능은 없습니다. 추가 도움말은 <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName> 문서를 참조하십시오.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="VBCompat"></a>   
### <a name="assembly-microsoftvisualbasiccompatibilitydll"></a>어셈블리: Microsoft.VisualBasic.Compatibility.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseControlArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseOcxArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ButtonArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CheckBoxArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CheckedListBoxArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ColorDialogArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ComboBoxArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DirListBox?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DirListBoxArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DriveListBox?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DriveListBoxArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FileListBox?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FileListBoxArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FixedLengthString?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FontDialogArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FormShowConstants?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.GroupBoxArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.HScrollBarArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ImageListArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.LabelArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListBoxArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListBoxItem?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListViewArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.LoadResConstants?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MaskedTextBoxArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MenuItemArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MouseButtonConstants?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.OpenFileDialogArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PanelArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PictureBoxArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PrintDialogArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ProgressBarArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.RadioButtonArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.RichTextBoxArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.SaveFileDialogArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ScaleMode?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ShiftConstants?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.StatusBarArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.StatusStripArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.Support?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TabControlArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TextBoxArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TimerArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolBarArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolStripArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolStripMenuItemArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TreeViewArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.VScrollBarArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebBrowserArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClass?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassContainingClassNotOptional?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassCouldNotFindEvent?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassNextItemCannotBeCurrentWebItem?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassNextItemRespondNotFound?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassUserWebClassNameNotOptional?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassWebClassFileNameNotOptional?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassWebItemNotValid?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItem?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemAssociatedWebClassNotOptional?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemClosingTagNotFound?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemCouldNotLoadEmbeddedResource?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemCouldNotLoadTemplateFile?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemNameNotOptional?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemNoTemplateSpecified?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemTooManyNestedTags?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemUnexpectedErrorReadingTemplateFile?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ZOrderConstants?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="VBCompatData"></a>   
### <a name="assembly-microsoftvisualbasiccompatibilitydatadll"></a>어셈블리: Microsoft.VisualBasic.Compatibility.Data.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.BOFActionEnum?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.EndOfRecordsetDelegate?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.EOFActionEnum?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.ErrorDelegate?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FetchCompleteDelegate?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FetchProgressDelegate?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FieldChangeCompleteDelegate?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.MoveCompleteDelegate?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.OrientationEnum?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.RecordChangeCompleteDelegate?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.RecordsetChangeCompleteDelegate?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeFieldDelegate?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeRecordDelegate?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeRecordsetDelegate?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillMoveDelegate?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODCArray?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseDataEnvironment?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BindingCollectionEnumerator?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CONNECTDATA?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBBINDING?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBCOLUMNINFO?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBID?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBinding?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBindingCollection?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBKINDENUM?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBPROPIDSET?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IAccessor?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IChapteredRowset?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IColumnsInfo?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IConnectionPoint?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IConnectionPointContainer?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IDataFormat?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IDataFormatDisp?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IEnumConnectionPoints?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IEnumConnections?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowPosition?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowPositionChange?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowset?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetChange?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetIdentity?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetInfo?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetNotify?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MBinding?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MBindingCollection?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.SRDescriptionAttribute?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UGUID?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UNAME?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UpdateMode?displayProperty=fullName>|[Microsoft.VisualBasic.Compatibility.VB6.\<member>는 더 이상 사용되지 않고 32비트 프로세스에서만 지원됩니다](https://msdn.microsoft.com/library/ee839621.aspx)를 참조하십시오.|  
  
 [맨 위로 이동](#introduction)  
  
<a name="visualc"></a>   
### <a name="assembly-microsoftvisualcdll"></a>어셈블리: Microsoft.VisualC.dll  
  
|형식|메시지|  
|----------|-------------|  
|<xref:Microsoft.VisualC.DebugInfoInPDBAttribute?displayProperty=fullName>|Microsoft.VisualC.dll은 사용되지 않는 어셈블리이며 이전 버전과의 호환성을 위해서만 존재합니다.|  
|<xref:Microsoft.VisualC.DecoratedNameAttribute?displayProperty=fullName>|Microsoft.VisualC.dll은 사용되지 않는 어셈블리이며 이전 버전과의 호환성을 위해서만 존재합니다.|  
|<xref:Microsoft.VisualC.IsConstModifier?displayProperty=fullName>|Microsoft.VisualC.dll은 사용되지 않는 어셈블리이며 이전 버전과의 호환성을 위해서만 존재합니다.|  
|<xref:Microsoft.VisualC.IsCXXReferenceModifier?displayProperty=fullName>|Microsoft.VisualC.dll은 사용되지 않는 어셈블리이며 이전 버전과의 호환성을 위해서만 존재합니다.|  
|<xref:Microsoft.VisualC.IsLongModifier?displayProperty=fullName>|Microsoft.VisualC.dll은 사용되지 않는 어셈블리이며 이전 버전과의 호환성을 위해서만 존재합니다.|  
|<xref:Microsoft.VisualC.IsSignedModifier?displayProperty=fullName>|Microsoft.VisualC.dll은 사용되지 않는 어셈블리이며 이전 버전과의 호환성을 위해서만 존재합니다.|  
|<xref:Microsoft.VisualC.IsVolatileModifier?displayProperty=fullName>|Microsoft.VisualC.dll은 사용되지 않는 어셈블리이며 이전 버전과의 호환성을 위해서만 존재합니다.|  
|<xref:Microsoft.VisualC.MiscellaneousBitsAttribute?displayProperty=fullName>|Microsoft.VisualC.dll은 사용되지 않는 어셈블리이며 이전 버전과의 호환성을 위해서만 존재합니다.|  
|<xref:Microsoft.VisualC.NeedsCopyConstructorModifier?displayProperty=fullName>|Microsoft.VisualC.dll은 사용되지 않는 어셈블리이며 이전 버전과의 호환성을 위해서만 존재합니다.|  
|<xref:Microsoft.VisualC.NoSignSpecifiedModifier?displayProperty=fullName>|Microsoft.VisualC.dll은 사용되지 않는 어셈블리이며 이전 버전과의 호환성을 위해서만 존재합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [클래스 라이브러리의 사용되지 않는 기능](../../../docs/framework/whats-new/whats-obsolete.md)   
 [사용되지 않는 멤버](../../../docs/framework/whats-new/obsolete-members.md)

