---
title: '&lt;bindingRedirect&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 08dc7a55b5b0c580f19d137496b9405fa4e18a5f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltbindingredirectgt-element"></a>&lt;bindingRedirect&gt; 요소
어셈블리 버전을 다른 버전으로 리디렉션합니다.  
  
 \<configuration>  
\<runtime>  
\<assemblyBinding>  
\<dependentAssembly >  
\<bindingRedirect >  
  
## <a name="syntax"></a>구문  
  
```xml  
   <bindingRedirect    
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`oldVersion`|필수 특성입니다.<br /><br /> 원래 요청된 어셈블리 버전을 지정합니다. 어셈블리 버전 번호의 형식은 *major.minor.build.revision*합니다. 이 버전 번호의 각 부분에 사용할 수 있는 값은 0부터 65535까지입니다.<br /><br /> 다음 형식으로 다양한 버전을 지정할 수도 있습니다.<br /><br /> *n.n.n.n-n.n.n.n*|  
|`newVersion`|필수 특성입니다.<br /><br /> 원래 요청 된 버전 형식에서 대신 사용할 어셈블리의 버전을 지정: *n.n.n.n*<br /><br /> 이 값은 `oldVersion`보다 이전 버전을 지정할 수 있습니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|없음||  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`assemblyBinding`|어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`dependentAssembly`|각 어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다. 각 어셈블리에 dependentAssembly 요소를 하나만 사용할 수 있습니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 강력한 이름의 어셈블리에 대해 .NET Framework 응용 프로그램을 빌드하면, 응용 프로그램은 새 버전이 있는 경우에도 런타임에 기본적으로 어셈블리의 원래 버전을 사용합니다. 그러나 어셈블리의 새 버전을 사용하도록 응용 프로그램을 구성할 수도 있습니다. 런타임에서 사용할 어셈블리 버전을 결정 하려면 이러한 파일을 사용 하는 방법에 대 한 세부 정보를 참조 하십시오. [런타임에서 어셈블리를 찾는 방법을](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)합니다.  
  
 `bindingRedirect` 요소에 여러 개의 `dependentAssembly` 요소를 사용하면 둘 이상의 어셈블리 버전을 리디렉션할 수 있습니다. 어셈블리의 새 버전에서 이전 버전으로 리디렉션할 수도 있습니다.  
  
 응용 프로그램 구성 파일에서 어셈블리 바인딩을 명시적으로 리디렉션하려면 보안 권한이 필요합니다. 이는 .NET Framework 어셈블리와 타사 어셈블리의 리디렉션 모두에 적용됩니다. 설정 하 여 권한 부여는 <xref:System.Security.Permissions.SecurityPermissionFlag> 에 플래그는 <xref:System.Security.Permissions.SecurityPermission>합니다. 자세한 내용은 참조 [어셈블리 바인딩 리디렉션 보안 권한](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 어셈블리 버전을 다른 버전으로 리디렉션하는 방법을 보여줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [어셈블리 버전 리디렉션](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
