---
title: '방법: 텍스트 파일에 이벤트 정보 쓰기(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs [Visual Studio], writing event information
- text files [Visual Basic], writing event information to a text file
- events [Visual Basic], writing event information to a text file
ms.assetid: 9ca7cc03-bf99-4933-9e5e-61ee28e9a6b4
ms.openlocfilehash: 3adb594ee42b7b1fad77a54af04bb9f37f30c19a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589060"
---
# <a name="how-to-write-event-information-to-a-text-file-visual-basic"></a><span data-ttu-id="f9bef-102">방법: 텍스트 파일에 이벤트 정보 쓰기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9bef-102">How to: Write Event Information to a Text File (Visual Basic)</span></span>
<span data-ttu-id="f9bef-103">`My.Application.Log` 및 `My.Log` 개체를 사용하여 응용 프로그램에서 발생하는 이벤트에 대한 정보를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bef-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="f9bef-104">이 예제에서는 `My.Application.Log.WriteEntry` 메서드를 사용하여 추적 정보를 로그 파일에 기록하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9bef-104">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information to a log file.</span></span>  
  
### <a name="to-add-and-configure-the-file-log-listener"></a><span data-ttu-id="f9bef-105">파일 로그 수신기를 추가하고 구성하려면</span><span class="sxs-lookup"><span data-stu-id="f9bef-105">To add and configure the file log listener</span></span>  
  
1.  <span data-ttu-id="f9bef-106">**솔루션 탐색기** 에서 app.config를 마우스 오른쪽 단추로 클릭하고 **열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bef-106">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="f9bef-107">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="f9bef-107">\- or -</span></span>  
  
     <span data-ttu-id="f9bef-108">app.config 파일이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="f9bef-108">If there is no app.config file:</span></span>  
  
    1.  <span data-ttu-id="f9bef-109">**프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bef-109">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="f9bef-110">**새 항목 추가** 대화 상자에서 **응용 프로그램 구성 파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bef-110">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="f9bef-111">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bef-111">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="f9bef-112">응용 프로그램 구성 파일에서 `<listeners>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bef-112">Locate the `<listeners>` section in the application configuration file.</span></span>  
  
     <span data-ttu-id="f9bef-113">최상위 \<configuration> 섹션 아래에 중첩된 \<system.diagnostics> 섹션 아래에서 이름 특성이 "DefaultSource"인 \<source> 섹션에 \<listeners> 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bef-113">You will find the \<listeners> section in the \<source> section with the name attribute "DefaultSource", which is nested under the \<system.diagnostics> section, which is nested under the top-level \<configuration> section.</span></span>  
  
3.  <span data-ttu-id="f9bef-114">다음 요소를 `<listeners>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bef-114">Add this element to that `<listeners>` section:</span></span>  
  
    ```xml  
    <add name="FileLogListener" />  
    ```  
  
4.  <span data-ttu-id="f9bef-115">최상위 `<configuration>` 섹션 아래에 중첩된 `<system.diagnostics>` 섹션에서 `<sharedListeners>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bef-115">Locate the `<sharedListeners>` section in the `<system.diagnostics>` section, nested under the top-level `<configuration>` section.</span></span>  
  
5.  <span data-ttu-id="f9bef-116">다음 요소를 `<sharedListeners>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bef-116">Add this element to that `<sharedListeners>` section:</span></span>  
  
    ```xml  
    <add name="FileLogListener"   
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
              Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,   
              PublicKeyToken=b03f5f7f11d50a3a"  
        initializeData="FileLogListenerWriter"  
        location="Custom"  
        customlocation="c:\temp\" />  
    ```  
  
     <span data-ttu-id="f9bef-117">`customlocation` 특성의 값을 로그 디렉터리로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bef-117">Change the value of the `customlocation` attribute to the log directory.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9bef-118">수신기 속성의 값을 설정하려면 속성과 이름이 같고 이름에 있는 모든 문자가 소문자인 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bef-118">To set the value of a listener property, use an attribute that has the same name as the property, with all letters in the name lowercase.</span></span> <span data-ttu-id="f9bef-119">예를 들어 `location` 및 `customlocation` 특성은 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> 및 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A> 속성의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bef-119">For example, the `location` and `customlocation` attributes set the values of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> and <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A> properties.</span></span>  
  
### <a name="to-write-event-information-to-the-file-log"></a><span data-ttu-id="f9bef-120">이벤트 정보를 파일 로그에 쓰려면</span><span class="sxs-lookup"><span data-stu-id="f9bef-120">To write event information to the file log</span></span>  
  
-   <span data-ttu-id="f9bef-121">`My.Application.Log.WriteEntry` 또는 `My.Application.Log.WriteException` 메서드를 사용하여 파일 로그에 정보를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="f9bef-121">Use the `My.Application.Log.WriteEntry` or `My.Application.Log.WriteException` method to write information to the file log.</span></span> <span data-ttu-id="f9bef-122">자세한 내용은 [방법: 로그 메시지 쓰기](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) 및 [방법: 예외 기록](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9bef-122">For more information, see [How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) and [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span></span>  
  
     <span data-ttu-id="f9bef-123">어셈블리에 대한 파일 로그 수신기를 구성하면 수신기는 `My.Application.Log`가 해당 어셈블리에서 쓰는 모든 메시지를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bef-123">After you configure the file log listener for an assembly, it receives all messages that `My.Application.Log` writes from that assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9bef-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9bef-124">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>  
 [<span data-ttu-id="f9bef-125">응용 프로그램 로그 작업</span><span class="sxs-lookup"><span data-stu-id="f9bef-125">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [<span data-ttu-id="f9bef-126">방법: 예외 기록</span><span class="sxs-lookup"><span data-stu-id="f9bef-126">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
