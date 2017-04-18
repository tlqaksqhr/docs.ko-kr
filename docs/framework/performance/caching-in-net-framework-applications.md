---
title: ".NET Framework 응용 프로그램에서 캐싱 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ASP.NET 캐싱"
  - "캐시[.NET Framework]"
  - "캐싱[ASP.NET]"
ms.assetid: c4b47ee0-4b82-4124-9bce-818088385e34
caps.latest.revision: 26
author: "tdykstra"
ms.author: "tdykstra"
manager: "wpickett"
caps.handback.revision: 26
---
# .NET Framework 응용 프로그램에서 캐싱
캐싱을 사용하면 빠른 액세스를 위해 데이터를 메모리에 저장할 수 있습니다.  데이터를 다시 액세스할 때는 응용 프로그램이 원래 소스에서 데이터를 검색하는 대신 캐시에서 데이터를 가져올 수 있습니다.  이렇게 하면 성능과 확장성을 향상시킬 수 있습니다.  또한 캐싱을 사용하면 데이터 소스를 일시적으로 사용할 수 없는 경우에도 데이터를 사용할 수 있습니다.  
  
 .NET Framework는 ASP.NET을 포함하여 Windows 클라이언트 및 서버 응용 프로그램의 성능과 확장성을 모두 향상시키기 위해 사용할 수 있는 캐싱 기능을 제공합니다.  
  
> [!NOTE]
>  [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 및 이전 버전의 ASP.NET에서는 <xref:System.Web.Caching> 네임스페이스에서 메모리 내 캐시 구현이 제공되었습니다.  이전 버전의 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서 캐싱은 <xref:System.Web> 네임스페이스에서만 제공되었기 때문에 ASP.NET 클래스에 대한 종속성이 필요했습니다.  .NET Framework 4에서는 <xref:System.Runtime.Caching> 네임스페이스에 웹 응용 프로그램 및 웹 이외의 응용 프로그램을 위해 디자인된 API가 포함되어 있습니다.  
  
## 데이터 캐싱  
 <xref:System.Runtime.Caching> 네임스페이스의 클래스를 사용하여 정보를 캐시할 수 있습니다.  이 네임스페이스의 캐싱 클래스는 다음과 같은 기능을 제공합니다.  
  
-   사용자 지정 캐시 구현을 만들기 위한 기반을 제공하는 추상 형식  
  
-   구체적인 메모리 내 개체 캐시 구현  
  
 추상 기본 캐싱 클래스\(<xref:System.Runtime.Caching.ObjectCache>\)는 다음과 같은 캐싱 작업을 정의합니다.  
  
-   캐시 엔트리 만들기 및 관리  
  
-   만료 및 제거 정보 지정  
  
-   캐시 엔트리의 변경에 대한 응답으로 발생한 이벤트 트리거  
  
 <xref:System.Runtime.Caching.MemoryCache> 클래스는 <xref:System.Runtime.Caching.ObjectCache> 클래스의 메모리 내 개체 캐시 구현입니다.  대부분의 캐싱 작업에 대해 <xref:System.Runtime.Caching.MemoryCache> 클래스를 사용할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Runtime.Caching.MemoryCache> 클래스는 <xref:System.Web.Caching> 네임스페이스에 정의된 ASP.NET 캐시 개체에 모델링됩니다.  따라서 내부 캐싱 논리는 이전 버전의 ASP.NET에 제공된 논리와 비슷합니다.  
  
 WPF 응용 프로그램에서 캐싱을 사용하는 방법에 대한 예는 [연습: WPF 응용 프로그램에서 응용 프로그램 데이터 캐싱](../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)을 참조하십시오.  
  
## ASP.NET 응용 프로그램의 캐싱  
 <xref:System.Runtime.Caching> 네임스페이스의 캐싱 클래스는 ASP.NET에서 데이터 캐싱을 위한 기능을 제공합니다.  
  
> [!NOTE]
>  응용 프로그램의 대상 플랫폼이 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 또는 이전 버전인 경우, <xref:System.Web.Caching> 네임스페이스에 정의된 캐싱 클래스를 사용해야 합니다.  자세한 내용은 [ASP.NET Caching Overview](../Topic/ASP.NET%20Caching%20Overview.md)을 참조하십시오.  
  
> [!NOTE]
>  새 응용 프로그램을 개발할 때는 <xref:System.Runtime.Caching.MemoryCache> 클래스를 사용하는 것이 좋습니다.  <xref:System.Runtime.Caching> 네임스페이스에 제공된 API는 <xref:System.Web.Caching.Cache> 네임스페이스에 제공된 API와 비슷합니다.  따라서 이전 버전의 ASP.NET에서 캐싱을 사용해 본 경우 익숙하게 API를 사용할 수 있습니다. ASP.NET 응용 프로그램에서 캐싱을 사용하는 방법에 대한 예는 [Walkthrough: Caching Application Data in ASP.NET](../Topic/Walkthrough:%20Caching%20Application%20Data%20in%20ASP.NET.md)을 참조하십시오.  
  
### 출력 캐싱  
 응용 프로그램 데이터를 수동으로 캐시하려면 ASP.NET에서 <xref:System.Runtime.Caching.MemoryCache> 클래스를 사용할 수 있습니다. ASP.NET에는 또한 페이지, 컨트롤 및 HTTP 응답의 생성된 출력을 메모리에 저장하는 출력 캐싱이 지원됩니다.  출력 캐싱은 ASP.NET 웹 페이지에서 선언적으로 구성하거나 Web.config 파일의 설정을 사용하여 구성할 수 있습니다.  자세한 내용은 [caching 요소에 대한 outputCache 요소\(ASP.NET 설정 스키마\)](http://msdn.microsoft.com/ko-kr/47cd2b47-316f-4dfd-bbf8-539be3066fee)을 참조하십시오.  
  
 ASP.NET을 사용하면 사용자 지정 출력 캐시 공급자를 만들어서 출력 캐싱을 확장할 수 있습니다.  사용자 지정 공급자를 사용하면 디스크, 클라우드 저장소 및 분산 캐시 엔진과 같은 다른 저장소 장치를 사용하여 캐시된 콘텐츠를 저장할 수 있습니다.  사용자 지정 출력 캐시 공급자를 만들려면 <xref:System.Web.Caching.OutputCacheProvider> 클래스에서 파생되는 클래스를 만들고 사용자 지정 출력 캐시 공급자를 사용하도록 응용 프로그램을 구성합니다.  
  
## WCF REST 서비스의 캐싱  
 WCF REST 서비스의 경우 .NET Framework를 사용하면 ASP.NET에서 제공되는 선언적 출력 캐싱의 장점을 얻을 수 있습니다. 이렇게 하면 WCF REST 서비스 작업의 응답을 캐시할 수 있습니다.  사용자가 캐시용으로 구성된 서비스에 HTTP GET 요청을 보내면 ASP.NET이 캐시된 응답을 다시 보내고 서비스 메서드가 호출되지 않습니다.  캐시가 만료된 후에는 다음에 사용자가 HTTP GET 요청을 보낼 때 서비스 메서드가 호출되고 응답이 다시 캐시됩니다.  
  
 또한 .NET Framework에서는 조건부 HTTP GET 캐싱을 구현할 수도 있습니다.  REST 시나리오에서 조건부 HTTP GET 요청은 [HTTP Specification](http://go.microsoft.com/fwlink/?LinkId=165800) 에 설명된 것처럼 지능적인 HTTP 캐싱을 구현하기 위해 서비스에서 자주 사용됩니다.  자세한 내용은 [Caching Support for WCF Web HTTP Services](http://go.microsoft.com/fwlink/?LinkId=184598)를 참조하십시오.  
  
## .NET Framework의 캐싱 확장  
 .NET Framework에서 캐싱은 확장 가능하도록 디자인되었습니다.  <xref:System.Runtime.Caching.ObjectCache> 클래스를 사용하면 사용자 지정 캐시 구현을 만들 수 있습니다.  이 클래스는 Windows Forms, WPF\(Windows Presentation Foundation\) 및 WCF\(Windows Communications Foundation\)를 포함한 모든 관리되는 응용 프로그램에 제공되는 멤버를 제공합니다.  이 방법은 다른 저장소 메커니즘을 사용하는 캐시 클래스를 만들기 위한 용도나 캐시 작업을 세부적으로 제어하려는 경우에 사용할 수 있습니다.  
  
 캐싱을 확장하려면 다음을 수행할 수 있습니다.  
  
-   <xref:System.Runtime.Caching.ObjectCache> 클래스에서 파생되는 사용자 지정 클래스를 만들고 파생된 클래스에서 사용자 지정 캐시 구현을 제공합니다.  
  
-   <xref:System.Runtime.Caching.MemoryCache> 클래스에서 파생되는 클래스를 만들고 파생된 클래스를 사용자 지정하거나 확장합니다.  이 작업을 수행 하는 방법의 예제를 보려면 [Caching Application Data by Using Multiple Cache Objects in an ASP.NET Application](http://blogs.msdn.com/aspnetue/archive/2010/03/22/caching-application-data-by-using-multiple-cache-objects-in-an-asp-net-application.aspx)을 참조하십시오.  
  
-   <xref:System.Web.Caching.OutputCacheProvider> 클래스에서 파생되는 클래스를 만들고 사용자 지정 출력 캐시 공급자를 사용하도록 응용 프로그램을 구성합니다.  
  
 자세한 내용은 Scott Guthrie의 블로그에서 [Extensible Output Caching with ASP.NET 4 \(VS 2010 and .NET 4.0 Series\)](http://go.microsoft.com/fwlink/?LinkId=185772) 항목을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Runtime.Caching.ObjectCache>   
 <xref:System.Runtime.Caching.MemoryCache>   
 [연습: WPF 응용 프로그램에서 응용 프로그램 데이터 캐싱](../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)   
 [Walkthrough: Caching Application Data in ASP.NET](../Topic/Walkthrough:%20Caching%20Application%20Data%20in%20ASP.NET.md)