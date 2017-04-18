---
title: "연습: WPF 응용 프로그램에서 응용 프로그램 데이터 캐싱 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "캐시[.NET Framework]"
  - "캐싱[WPF]"
  - "연습[WPF], 캐싱"
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# 연습: WPF 응용 프로그램에서 응용 프로그램 데이터 캐싱
캐싱을 사용하면 빠른 액세스를 위해 데이터를 메모리에 저장할 수 있습니다.  데이터에 다시 액세스하면 응용 프로그램이 원래 소스에서 데이터를 검색하는 대신 캐시에서 데이터를 가져올 수 있습니다.  이렇게 하면 성능과 확장성을 향상시킬 수 있습니다.  또한 캐싱을 사용하면 데이터 소스를 일시적으로 사용할 수 없는 경우에도 데이터를 사용할 수 있습니다.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 에서 캐싱을 사용할 수 있도록 하는 클래스를 제공 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 응용 프로그램입니다.  이러한 클래스에는 <xref:System.Runtime.Caching>네임스페이스입니다.  
  
> [!NOTE]
>  <xref:System.Runtime.Caching> 네임스페이스는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]에서 새로 추가되었습니다.  이 네임스페이스는 모든 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 응용 프로그램에서 캐싱을 사용할 수 있도록 합니다.  이전 버전의 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서 캐싱은 <xref:System.Web> 네임스페이스에서만 제공되었기 때문에 ASP.NET 클래스에 대한 종속성이 필요했습니다.  
  
 이 연습에서는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서 사용할 수 있는 캐싱 기능을 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램의 일부로 사용하는 방법을 보여 줍니다.  이 연습에서는 텍스트 파일의 내용을 캐시합니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   WPF 응용 프로그램 프로젝트 만들기  
  
-   [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]에 대한 참조 추가  
  
-   캐시 초기화  
  
-   텍스트 파일의 내용이 포함된 캐시 엔트리 추가  
  
-   캐시 엔트리에 대한 제거 정책 제공  
  
-   캐시된 파일의 경로를 모니터링하고 모니터링된 항목의 변경 내용을 캐시 인스턴스에 알리기  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음과 같은 요건이 필요합니다.  
  
-   Microsoft [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]  
  
-   적은 양의 텍스트가 포함된 텍스트 파일.  이 텍스트 파일의 내용을 메시지 상자에 표시합니다. 연습에 나오는 코드에서는 다음 파일을 사용하고 있다고 가정합니다.  
  
     `c:\cache\cacheText.txt`  
  
     그러나 아무 텍스트 파일이나 사용할 수 있으며 이 연습의 코드를 약간 변경할 수도 있습니다.  
  
## WPF 응용 프로그램 프로젝트 만들기  
 먼저 WPF 응용 프로그램 프로젝트를 만듭니다.  
  
#### WPF 응용 프로그램을 만들려면  
  
1.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]를 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 클릭하고 **새 프로젝트**를 클릭합니다.  
  
     **새 프로젝트** 대화 상자가 표시됩니다.  
  
3.  **설치된 템플릿**에서 사용할 프로그래밍 언어\(**Visual Basic** 또는 **Visual C\#**\)를 선택합니다.  
  
4.  **새 프로젝트** 대화 상자에서 **WPF 응용 프로그램**을 선택합니다.  
  
    > [!NOTE]
    >  **WPF 응용 프로그램** 템플릿이 표시되지 않는 경우 WPF를 지원하는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]버전을 대상으로 하는지 확인합니다.  **새 프로젝트** 대화 상자의 목록에서 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]를 선택합니다.  
  
5.  **이름** 텍스트 상자에 프로젝트의 이름을 입력합니다.  예를 들어 WPFCaching을 입력합니다.  
  
6.  **솔루션용 디렉터리 만들기** 확인란을 선택합니다.  
  
7.  **확인**을 클릭합니다.  
  
     WPF Designer가 **디자인** 뷰에서 열리고 MainWindow.xaml 파일이 표시됩니다.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 **My Project** 폴더, Application.xaml 파일 및 MainWindow.xaml 파일을 만듭니다.  
  
## .NET Framework 대상 지정 및 캐싱 어셈블리에 대한 참조 추가  
 기본적으로 WPF 응용 프로그램은 [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]을 대상으로 합니다.  WPF 응용 프로그램에서 <xref:System.Runtime.Caching> 네임스페이스를 사용하려면 해당 응용 프로그램에서 [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]이 아닌 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]를 대상으로 하고 네임스페이스에 대한 참조를 추가해야 합니다.  
  
 따라서 다음 단계에서는 .NET Framework 대상을 변경하고 <xref:System.Runtime.Caching> 네임스페이스에 대한 참조를 추가합니다.  
  
> [!NOTE]
>  .NET Framework 대상을 변경하는 절차는 Visual Basic 프로젝트 및 Visual C\# 프로젝트에서와 다릅니다.  
  
#### Visual Basic에서 대상 .NET Framework를 변경하려면  
  
1.  **솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.  
  
     응용 프로그램의 속성 창이 표시됩니다.  
  
2.  **컴파일** 탭을 클릭합니다.  
  
3.  창의 아래쪽에서 **고급 컴파일 옵션...**을 클릭합니다.  
  
     **고급 컴파일러 설정** 대화 상자가 표시됩니다.  
  
4.  에 있는  **대상 프레임 워크 \(모든 구성\)** 목록에서 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  \(선택 하지 않은 [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]입니다.\)  
  
5.  **확인**을 클릭합니다.  
  
     **대상 프레임워크 변경** 대화 상자가 표시됩니다.  
  
6.  **대상 프레임워크 변경** 대화 상자에서 **예**를 클릭합니다.  
  
     프로젝트가 닫힌 후 다시 열립니다.  
  
7.  다음 단계에 따라 캐싱 어셈블리에 대한 참조를 추가합니다.  
  
    1.  **솔루션 탐색기**에서 프로젝트의 이름을 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다.  
  
    2.  **.NET** 탭을 선택하고 `System.Runtime.Caching`을 선택한 다음 **확인**을 클릭합니다.  
  
#### Visual C\# 프로젝트에서 대상 .NET Framework를 변경하려면  
  
1.  **솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
     응용 프로그램의 속성 창이 표시됩니다.  
  
2.  **응용 프로그램** 탭을 클릭합니다.  
  
3.  **대상 프레임워크** 목록에서 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]를 선택합니다.  **.NET Framework 4 Client Profile**을 선택하지 마십시오.  
  
4.  다음 단계에 따라 캐싱 어셈블리에 대한 참조를 추가합니다.  
  
    1.  **참조** 폴더를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다.  
  
    2.  **.NET** 탭을 선택하고 `System.Runtime.Caching`을 선택한 다음 **확인**을 클릭합니다.  
  
## WPF 창에 단추 추가  
 다음에는 단추 컨트롤을 추가하고 단추의 `Click` 이벤트에 대한 이벤트 처리기를 만듭니다.  나중에 이 단추를 클릭하면 텍스트 파일의 내용이 캐시되고 표시되도록 하는 코드를 추가합니다.  
  
#### 단추 컨트롤을 추가하려면  
  
1.  **솔루션 탐색기**에서 MainWindow.xaml 파일을 두 번 클릭하여 엽니다.  
  
2.  **도구 상자**의 **공용 WPF 컨트롤**에서 `Button` 컨트롤을 `MainWindow` 창으로 끕니다.  
  
3.  **속성** 창에서 `Button` 컨트롤의 `Content` 속성을 '캐시 가져오기'로 설정합니다.  
  
## 캐시 초기화 및 엔트리 캐싱  
 다음에는 아래 작업을 수행하는 코드를 추가합니다.  
  
-   캐시 클래스의 인스턴스 만들기\(새 <xref:System.Runtime.Caching.MemoryCache> 개체 인스턴스화\)  
  
-   캐시에서 <xref:System.Runtime.Caching.HostFileChangeMonitor> 개체를 사용하여 텍스트 파일의 변경 내용을 모니터링하도록 지정  
  
-   텍스트 파일을 읽고 파일 내용을 캐시 엔트리로 캐시  
  
-   캐시된 텍스트 파일의 내용 표시  
  
#### 캐시 개체를 만들려면  
  
1.  방금 추가한 단추를 두 번 클릭하여 MainWindow.xaml.cs 또는 MainWindow.Xaml.vb 파일에 이벤트 처리기를 만듭니다.  
  
2.  파일 맨 위의 클래스 선언 앞에 다음 `Imports`\(Visual Basic의 경우\) 및 `using`\(C\#의 경우\) 문을 추가합니다.  
  
    ```csharp  
    using System.Runtime.Caching;  
    using System.IO;  
    ```  
  
    ```vb  
    Imports System.Runtime.Caching  
    Imports System.IO  
    ```  
  
3.  이벤트 처리기에 다음 코드를 추가하여 캐시 개체를 인스턴스화합니다.  
  
    ```csharp  
    ObjectCache cache = MemoryCache.Default;  
    ```  
  
    ```vb  
    Dim cache As ObjectCache = MemoryCache.Default  
    ```  
  
     <xref:System.Runtime.Caching.ObjectCache> 클래스는 메모리 내 개체 캐시를 제공하는 기본 제공 클래스입니다.  
  
4.  `filecontents`라는 캐시 엔트리의 내용을 읽는 다음 코드를 추가합니다.  
  
    ```vb  
    Dim fileContents As String = TryCast(cache("filecontents"), String)  
    ```  
  
    ```csharp  
    string fileContents = cache["filecontents"] as string;  
    ```  
  
5.  `filecontents`라는 캐시 엔트리가 있는지 여부를 확인하는 다음 코드를 추가합니다.  
  
    ```vb  
    If fileContents Is Nothing Then  
  
    End If  
    ```  
  
    ```csharp  
    if (fileContents == null)  
    {  
  
    }  
    ```  
  
     지정한 캐시 엔트리가 없으면 텍스트 파일을 읽고 이를 캐시에 캐시 엔트리로 추가해야 합니다.  
  
6.  `if/then` 블록에서 다음 코드를 추가하여 캐시 엔트리가 10초 후 만료되도록 지정하는 새 <xref:System.Runtime.Caching.CacheItemPolicy> 개체를 만듭니다.  
  
    ```vb  
    Dim policy As New CacheItemPolicy()  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)  
    ```  
  
    ```csharp  
    CacheItemPolicy policy = new CacheItemPolicy();  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);  
    ```  
  
     제거 또는 만료 정보를 제공하지 않을 경우 기본값은 <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>입니다. 즉, 캐시 엔트리가 절대 시간에 따라 만료되지 않습니다.  대신 메모리가 부족할 때만 캐시 엔트리가 만료됩니다.  가장 좋은 방법은 항상 절대 또는 상대\(siding\) 만료를 명시적으로 제공하는 것입니다.  
  
7.  `if/then` 블록 내에 있는 이전 단계에서 추가한 코드 뒤에 다음 코드를 추가하여 모니터링할 파일 경로의 컬렉션을 만들고 컬렉션에 텍스트 파일의 경로를 추가합니다.  
  
    ```vb  
    Dim filePaths As New List(Of String)()  
    filePaths.Add("c:\cache\cacheText.txt")  
    ```  
  
    ```csharp  
    List<string> filePaths = new List<string>();  
    filePaths.Add("c:\\cache\\cacheText.txt");  
    ```  
  
    > [!NOTE]
    >  사용할 텍스트 파일이 `c:\cache\cacheText.txt`가 아닌 경우 사용할 텍스트 파일의 경로를 지정합니다.  
  
8.  이전 단계에서 추가한 코드 뒤에 다음 코드를 추가하여 캐시 엔트리에 대한 변경 모니터의 컬렉션에 새 <xref:System.Runtime.Caching.HostFileChangeMonitor> 개체를 추가합니다.  
  
    ```vb  
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))  
    ```  
  
    ```csharp  
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));  
    ```  
  
     <xref:System.Runtime.Caching.HostFileChangeMonitor> 개체는 텍스트 파일의 경로를 모니터링하고 변경 내용이 있으면 캐시에 알립니다.  이 예제의 캐시 엔트리는 파일 내용이 변경될 경우 만료됩니다.  
  
9. 이전 단계에서 추가한 코드 뒤에 텍스트 파일의 내용을 읽는 다음 코드를 추가합니다.  
  
    ```vb  
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()  
    ```  
  
    ```csharp  
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + + "\n" + DateTime.Now;   
    ```  
  
     캐시 엔트리가 만료되는 시기를 확인할 수 있도록 날짜 및 시간 타임스탬프가 추가됩니다.  
  
10. 이전 단계에서 추가한 코드 뒤에 파일 내용을 캐시 엔트리에 <xref:System.Runtime.Caching.CacheItem> 인스턴스로 삽입하는 다음 코드를 추가합니다.  
  
    ```vb  
    cache.Set("filecontents", fileContents, policy)  
    ```  
  
    ```csharp  
    cache.Set("filecontents", fileContents, policy);  
    ```  
  
     앞에서 만든 <xref:System.Runtime.Caching.CacheItemPolicy> 개체를 매개 변수로 전달하여 캐시 엔트리를 제거할 방법에 대한 정보를 지정합니다.  
  
11. `if/then` 블록 뒤에 캐시된 파일 내용을 메시지 상자에 표시하는 다음 코드를 추가합니다.  
  
    ```vb  
    MessageBox.Show(fileContents)  
    ```  
  
    ```csharp  
    MessageBox.Show(fileContents);  
    ```  
  
12. **빌드** 메뉴에서 **WPFCaching 빌드**를 클릭하여 프로젝트를 빌드합니다.  
  
## WPF 응용 프로그램에서 캐싱 테스트  
 이제 응용 프로그램을 테스트할 수 있습니다.  
  
#### WPF 응용 프로그램에서 캐싱을 테스트하려면  
  
1.  Ctrl\+F5를 눌러 응용 프로그램을 실행합니다.  
  
     `MainWindow` 창이 표시됩니다.  
  
2.  **캐시 가져오기**를 클릭합니다.  
  
     텍스트 파일에서 캐시된 내용이 메시지 상자에 표시됩니다.  파일의 타임스탬프를 확인합니다  
  
3.  메시지 상자를 닫고 **캐시 가져오기**를 다시 클릭합니다.  
  
     타임스탬프가 변경되지 않았습니다.  이는 캐시된 내용이 표시되었음을 나타냅니다.  
  
4.  10초 이상 기다렸다가 **캐시 가져오기**를 다시 클릭합니다.  
  
     이번에는 새 타임스탬프가 표시됩니다.  이는 정책에 따라 캐시 엔트리가 만료되고 새 캐시 내용이 표시되었음을 나타냅니다.  
  
5.  텍스트 편집기에서 만든 텍스트 파일을 엽니다.  아직 아무 것도 변경하면 안 됩니다.  
  
6.  메시지 상자를 닫고 **캐시 가져오기**를 다시 클릭합니다.  
  
     타임스탬프를 다시 확인합니다.  
  
7.  텍스트 파일을 변경한 다음 파일을 저장합니다.  
  
8.  메시지 상자를 닫고 **캐시 가져오기**를 다시 클릭합니다.  
  
     이 메시지 상자에는 텍스트 파일의 업데이트된 내용과 새 타임스탬프가 포함됩니다.  이는 절대 제한 시간이 만료되지 않았더라도 파일을 변경한 후 즉시 호스트 파일 변경 모니터가 캐시 엔트리를 제거했음을 나타냅니다.  
  
    > [!NOTE]
    >  파일을 변경할 시간이 더 필요한 경우 제거 시간을 20초 이상으로 늘릴 수 있습니다.  
  
## 코드 예제  
 이 연습을 마치면 프로젝트의 코드가 다음과 같이 작성됩니다.  
  
 [!code-csharp[CachingWPFApplications#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]  
  
## 참고 항목  
 <xref:System.Runtime.Caching.MemoryCache>   
 <xref:System.Runtime.Caching.ObjectCache>   
 <xref:System.Runtime.Caching>   
 [.NET Framework 응용 프로그램에서 캐싱](../../../../docs/framework/performance/caching-in-net-framework-applications.md)