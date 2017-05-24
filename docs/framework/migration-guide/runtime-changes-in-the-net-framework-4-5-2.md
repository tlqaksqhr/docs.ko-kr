---
title: ".NET Framework 4.5.2의 런타임 변경 내용 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 94ac01ea-8b12-44d2-b12b-5220a5d14d87
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 247fbf574f13985fc941f252c0a6e7268194c079
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="runtime-changes-in-the-net-framework-452"></a>.NET Framework 4.5.2의 런타임 변경 내용
드문 경우지만 런타임 변경 내용이 .NET Framework 이전 버전을 대상으로 하지만 .NET Framework 4.5.2 런타임에 실행되는 기존 앱에 영향을 줄 수 있습니다. 다음 영역에 이러한 변경 내용이 포함되어 있습니다.  
  
-   [ASP.NET](#ASP_NET)  
  
-   [Entity Framework](#EF)  
  
<a name="ASP_NET"></a>   
## <a name="aspnet-runtime-changes"></a>ASP.NET 런타임 변경 내용  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|[페이지 요소](http://msdn.microsoft.com/en-us/4123bb66-3fe4-4d62-b70e-33758656b458)의 `enableViewStateMac` 특성|ASP.NET에서 개발자는 더 이상 다음을 지정할 수 없습니다.<br /><br /> `<pages enableViewStateMac="false" />`<br /><br /> 또는<br /><br /> `<@Page EnableViewStateMac="false" %>`|포함된 뷰 상태가 사용된 모든 요청에 뷰 상태 MAC(메시지 인증 코드)가 적용됩니다. <xref:System.Web.UI.Page.EnableViewStateMac%2A> 속성이 `false`로 명시적으로 설정된 앱에만 영향을 줍니다.<br /><br /> 자세한 내용은 [뷰 상태 MAC(메시지 인증 코드) 오류 해결](http://support.microsoft.com/kb/2915218)을 참조하세요.|주요함|  
  
<a name="EF"></a>   
## <a name="entity-framework-runtime-changes"></a>Entity Framework 런타임 변경 내용  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|QueryView를 통한 관계|관련 엔터티를 쿼리의 일부로 포함시키려는 0..1 탐색 속성으로 QueryView가 포함된 쿼리를 앱에서 실행하는 경우(예: <xref:System.StackOverflowException> 호출) Entity Framework가 더 이상 `.Include(e=>e.RelatedNavProp)` 예외를 throw하지 않습니다.|이러한 변경은 `.Include`를 호출하는 쿼리를 실행할 때 1-0..1 관계가 있는 QueryView를 사용하는 코드에만 영향을 줍니다. 이 변경으로 인해 안정성이 향상되며 거의 모든 앱에는 영향을 주지 않습니다. 하지만 이 변경으로 예기치 않은 동작이 발생하면 다음 항목을 앱 구성 파일의 `<appSettings>` 섹션에 추가하여 이 기능을 비활성화할 수 있습니다.<br /><br /> `<add key="EntityFramework_SimplifyUserSpecifiedViews"  value="false" />`|Microsoft Edge|  
  
## <a name="see-also"></a>참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-2.md)   
 [4.5의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [4.5.1의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)
