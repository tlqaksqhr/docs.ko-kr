---
title: ".NET Framework 4.5.1의 변경 내용 대상 변경 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8087326d-77e9-4804-ba33-ff1bb1bec2b8
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# .NET Framework 4.5.1의 변경 내용 대상 변경
드문 경우지만 대상 다시 지정 변경 내용은 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]을 대상으로 다시 컴파일되는 앱에 영향을 줄 수 있습니다. 이러한 변경 내용은 이전 버전의 .NET Framework를 대상으로 하지만 버전 4.5.1에서 실행되는 이진 파일에 영향을 주지 않습니다.[!INCLUDE[net_v451](../../../includes/net-v451-md.md)]의 다음 영역에 대상 다시 지정 변경 내용이 포함되어 있습니다.  
  
-   [핵심](#Core)  
  
-   [ADO.NET](#ADO)  
  
-   [MSBuild](#MSBuild)  
  
 다음 테이블의 범위 열에는 각 변경 내용의 영향력이 지정되어 있습니다.  
  
-   주요함 다수의 앱에 영향을 주거나 코드를 대폭 수정해야 하는 중요한 변경 내용입니다. 이 범주에 속한 대상 다시 지정 변경 내용은 없습니다.  
  
-   사소함 소수의 앱에 영향을 주거나 코드를 약간만 수정해야 하는 변경 내용입니다.  
  
-   특별한 경우 일반적이지 않은 매우 특별한 시나리오의 앱에 영향을 주는 변경 내용입니다.  
  
-   투명 앱 개발자나 사용자에게 뚜렷한 영향을 주지 않는 변경 내용입니다. 이 변경 내용으로 인한 앱 수정은 필요하지 않습니다.  
  
<a name="Core"></a>   
## 코어 대상 다시 지정 변경 내용  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|<xref:System.ObsoleteAttribute?displayProperty=fullName> 특성|Windows 메타데이터 라이브러리\(.winmd 파일\)를 만들 때 <xref:System.ObsoleteAttribute> 특성은 <xref:System.ObsoleteAttribute> 및 [Windows.Foundation.DeprecatedAttribute](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.deprecatedattribute.aspx) 둘 다로 내보내집니다.|<xref:System.ObsoleteAttribute> 특성이 사용된 기존 소스 코드를 다시 컴파일하면 C\+\+\/CX 또는 JavaScript의 해당 코드가 사용될 때 경고가 발생할 수 있습니다.<br /><br /> 관리 어셈블리의 코드에 <xref:System.ObsoleteAttribute> 및 [Windows.Foundation.DeprecatedAttribute](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.deprecatedattribute.aspx)를 둘 다 적용하지 않는 것이 좋습니다. 그럴 경우 빌드 경고가 발생할 수 있습니다.<br /><br /> 자세한 내용은 <xref:System.ObsoleteAttribute> 참조 항목을 참조하세요.|가장자리|  
  
<a name="ADO"></a>   
## ADO.NET 대상 다시 지정 변경 내용  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|<xref:System.Data.Common.DbParameter?displayProperty=fullName> 클래스|<xref:System.Data.Common.DbParameter.Precision%2A?displayProperty=fullName>과 <xref:System.Data.Common.DbParameter.Scale%2A?displayProperty=fullName>은 공용 가상 속성으로 구현됩니다. 이들은 명시적 인터페이스 구현에 해당하는 <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision%2A?displayProperty=fullName>과 <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale%2A?displayProperty=fullName>로 대체됩니다.|이 변경 내용은 ADO.NET 데이터베이스 공급자를 만드는 개발자에게만 영향을 줍니다.|가장자리|  
  
<a name="MSBuild"></a>   
## MSBuild 대상 다시 지정 변경 내용  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|`ResolveAssemblyReference` 작업|이 작업은 참조 또는 해당 종속성이 앱 아키텍처와 일치하지 않음을 나타내는 경고 MSB3270을 내보냅니다. 예를 들어 `anycpu` 옵션으로 컴파일된 앱에 x86 참조가 포함된 경우 이 경고가 발생합니다. 이로 인해 앱의 런타임 오류가 발생할 수 있습니다\(앱이 x64 프로세스로 배포된 경우\).|영향에는 다음 두 가지 영역이 있습니다.<br /><br /> -   다시 컴파일하면 앱이 이전 MSBuild 버전에서 컴파일되었을 때는 나타나지 않았던 경고가 생성됩니다. 하지만 런타임 오류가 발생한 소스를 경고에서 확인할 수 있으므로 이 문제를 조사하여 해결할 수 있습니다.<br />-   경고가 오류로 처리되면 앱을 컴파일할 수 없습니다.|사소함|  
  
## 참고 항목  
 [런타임 변경 내용](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)   
 [4.5의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [4.5.2의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)