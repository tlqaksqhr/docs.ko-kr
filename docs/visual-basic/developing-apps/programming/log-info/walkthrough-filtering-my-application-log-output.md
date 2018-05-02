---
title: My.Application.Log 출력 필터링(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Log object, filtering output
- My.Application.Log object, filtering output
- application event logs, output filtering
ms.assetid: 2c0a457a-38a4-49e1-934d-a51320b7b4ca
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6c048578b320fedd2153aee7b466b1494551abe0
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-filtering-myapplicationlog-output-visual-basic"></a><span data-ttu-id="25a3c-102">연습: My.Application.Log 출력 필터링(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25a3c-102">Walkthrough: Filtering My.Application.Log Output (Visual Basic)</span></span>
<span data-ttu-id="25a3c-103">이 연습에서는 `My.Application.Log` 개체에 대한 기본 로그 필터링을 변경하여 `Log` 개체에서 수신기로 전달되는 정보 및 수신기가 작성하는 정보를 제어하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-103">This walkthrough demonstrates how to change the default log filtering for the `My.Application.Log` object, to control what information is passed from the `Log` object to the listeners and what information is written by the listeners.</span></span> <span data-ttu-id="25a3c-104">구성 정보가 응용 프로그램의 구성 파일에 저장되므로 응용 프로그램을 빌드한 후에도 로깅 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-104">You can change the logging behavior even after building the application, because the configuration information is stored in the application's configuration file.</span></span>  
  
## <a name="getting-started"></a><span data-ttu-id="25a3c-105">시작</span><span class="sxs-lookup"><span data-stu-id="25a3c-105">Getting Started</span></span>  
 <span data-ttu-id="25a3c-106">`My.Application.Log`에서 작성하는 각 메시지에는 연결된 심각도 수준이 있으며, 필터링 메커니즘은 로그 출력을 제어하는 데 이를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-106">Each message that `My.Application.Log` writes has an associated severity level, which filtering mechanisms use to control the log output.</span></span> <span data-ttu-id="25a3c-107">이 샘플 응용 프로그램은 `My.Application.Log` 메서드를 사용하여 서로 다른 심각도 수준으로 여러 로그 메시지를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-107">This sample application uses `My.Application.Log` methods to write several log messages with different severity levels.</span></span>  
  
#### <a name="to-build-the-sample-application"></a><span data-ttu-id="25a3c-108">샘플 응용 프로그램을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="25a3c-108">To build the sample application</span></span>  
  
1.  <span data-ttu-id="25a3c-109">새 Visual Basic Windows 응용 프로그램 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-109">Open a new Visual Basic Windows Application project.</span></span>  
  
2.  <span data-ttu-id="25a3c-110">Button1이라는 단추를 Form1에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-110">Add a button named Button1 to Form1.</span></span>  
  
3.  <span data-ttu-id="25a3c-111">Button1에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-111">In the <xref:System.Windows.Forms.Control.Click> event handler for Button1, add the following code:</span></span>  
  
     [!code-vb[VbVbcnMyApplicationLogFiltering#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-filtering-my-application-log-output_1.vb)]  
  
4.  <span data-ttu-id="25a3c-112">디버거에서 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-112">Run the application in the debugger.</span></span>  
  
5.  <span data-ttu-id="25a3c-113">**Button1**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-113">Press **Button1**.</span></span>  
  
     <span data-ttu-id="25a3c-114">응용 프로그램이 다음 정보를 응용 프로그램의 디버그 출력 및 로그 파일에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-114">The application writes the following information to the application's debug output and log file.</span></span>  
  
     `DefaultSource Information: 0 : In Button1_Click`  
  
     `DefaultSource Error: 2 : Error in the application.`  
  
6.  <span data-ttu-id="25a3c-115">응용 프로그램을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-115">Close the application.</span></span>  
  
     <span data-ttu-id="25a3c-116">응용 프로그램의 디버그 출력 창을 보는 방법에 대한 자세한 내용은 [출력 창](/visualstudio/ide/reference/output-window)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25a3c-116">For information on how to view the application's debug output window, see [Output Window](/visualstudio/ide/reference/output-window).</span></span> <span data-ttu-id="25a3c-117">응용 프로그램 로그 파일의 위치에 대한 자세한 내용은 [연습: My.Application.Log가 정보를 기록하는 위치 확인](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25a3c-117">For information on the location of the application's log file, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="25a3c-118">기본적으로 응용 프로그램을 닫으면 응용 프로그램이 로그 파일 출력을 플러시합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-118">By default, the application flushes the log-file output when the application closes.</span></span>  
  
     <span data-ttu-id="25a3c-119">위의 예제에서 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> 메서드에 대한 두 번째 호출 및 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> 메서드에 대한 호출은 로그 출력을 생성하지만, `WriteEntry` 메서드에 대한 첫 번째 및 마지막 호출은 로그 출력을 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-119">In the example above, the second call to the <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> method and the call to the <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> method produces log output, while the first and last calls to the `WriteEntry` method do not.</span></span> <span data-ttu-id="25a3c-120">`WriteEntry` 및 `WriteException`의 심각도 수준은 "정보" 및 "오류"이므로, 둘 다 `My.Application.Log` 개체의 기본 로그 필터링에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-120">This is because the severity levels of `WriteEntry` and `WriteException` are "Information" and "Error", both of which are allowed by the `My.Application.Log` object's default log filtering.</span></span> <span data-ttu-id="25a3c-121">그러나 "시작" 및 "중지" 심각도 수준의 이벤트는 로그 출력 생성이 금지됩니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-121">However, events with "Start" and "Stop" severity levels are prevented from producing log output.</span></span>  
  
## <a name="filtering-for-all-myapplicationlog-listeners"></a><span data-ttu-id="25a3c-122">모든 My.Application.Log 수신기에 대한 필터링</span><span class="sxs-lookup"><span data-stu-id="25a3c-122">Filtering for All My.Application.Log Listeners</span></span>  
 <span data-ttu-id="25a3c-123">`My.Application.Log` 개체는 `DefaultSwitch`라고 명명된 <xref:System.Diagnostics.SourceSwitch>를 사용하여 `WriteEntry` 및 `WriteException` 메서드에서 로그 수신기로 전달할 메시지를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-123">The `My.Application.Log` object uses a <xref:System.Diagnostics.SourceSwitch> named `DefaultSwitch` to control which messages it passes from the `WriteEntry` and `WriteException` methods to the log listeners.</span></span> <span data-ttu-id="25a3c-124">해당 값을 <xref:System.Diagnostics.SourceLevels> 열거형 값 중 하나로 설정하여 응용 프로그램의 구성 파일에서 `DefaultSwitch`를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-124">You can configure `DefaultSwitch` in the application's configuration file by setting its value to one of the <xref:System.Diagnostics.SourceLevels> enumeration values.</span></span> <span data-ttu-id="25a3c-125">기본적으로 값은 "정보"입니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-125">By default, its value is "Information".</span></span>  
  
 <span data-ttu-id="25a3c-126">다음 표는 특정 `DefaultSwitch` 설정이 지정된 경우 로그가 메시지를 수신기에 기록하는 데 필요한 심각도 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-126">This table shows the severity level required for Log to write a message to the listeners, given a particular `DefaultSwitch` setting.</span></span>  
  
|<span data-ttu-id="25a3c-127">DefaultSwitch 값</span><span class="sxs-lookup"><span data-stu-id="25a3c-127">DefaultSwitch Value</span></span>|<span data-ttu-id="25a3c-128">출력에 필요한 메시지 심각도</span><span class="sxs-lookup"><span data-stu-id="25a3c-128">Message severity required for output</span></span>|  
|---|---| 
|`Critical`|`Critical`|  
|`Error`|<span data-ttu-id="25a3c-129">`Critical` 또는 `Error`</span><span class="sxs-lookup"><span data-stu-id="25a3c-129">`Critical` or `Error`</span></span>|  
|`Warning`|<span data-ttu-id="25a3c-130">`Critical`, `Error`또는 `Warning`</span><span class="sxs-lookup"><span data-stu-id="25a3c-130">`Critical`, `Error`, or `Warning`</span></span>|  
|`Information`|<span data-ttu-id="25a3c-131">`Critical`, `Error`, `Warning` 또는 `Information`</span><span class="sxs-lookup"><span data-stu-id="25a3c-131">`Critical`, `Error`, `Warning`, or `Information`</span></span>|  
|`Verbose`|<span data-ttu-id="25a3c-132">`Critical`, `Error`, `Warning`, `Information` 또는 `Verbose`</span><span class="sxs-lookup"><span data-stu-id="25a3c-132">`Critical`, `Error`, `Warning`, `Information`, or `Verbose`</span></span>|  
|`ActivityTracing`|<span data-ttu-id="25a3c-133">`Start`, `Stop`, `Suspend`, `Resume` 또는 `Transfer`</span><span class="sxs-lookup"><span data-stu-id="25a3c-133">`Start`, `Stop`, `Suspend`, `Resume`, or `Transfer`</span></span>|  
|`All`|<span data-ttu-id="25a3c-134">모든 메시지를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-134">All messages are allowed.</span></span>|  
|`Off`|<span data-ttu-id="25a3c-135">모든 메시지를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-135">All messages are blocked.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="25a3c-136">`WriteEntry` 및 `WriteException` 메서드는 각각 심각도 수준을 지정하지 않는 오버로드를 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-136">The `WriteEntry` and `WriteException` methods each have an overload that does not specify a severity level.</span></span> <span data-ttu-id="25a3c-137">`WriteEntry` 오버로드에 대한 암시적 심각도 수준은 "정보"이며, `WriteException` 오버로드에 대한 암시적 심각도 수준은 "오류"입니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-137">The implicit severity level for the `WriteEntry` overload is "Information", and the implicit severity level for the `WriteException` overload is "Error".</span></span>  
  
 <span data-ttu-id="25a3c-138">다음 표는 이전 예제에 나와 있는 로그 출력을 설명합니다. 기본 `DefaultSwitch` 설정이 "정보"인 경우 `WriteEntry` 메서드에 대한 두 번째 호출 및 `WriteException` 메서드에 대한 호출만이 로그 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-138">This table explains the log output shown in the previous example: with the default `DefaultSwitch` setting of "Information", only the second call to the `WriteEntry` method and the call to the `WriteException` method produce log output.</span></span>  
  
#### <a name="to-log-only-activity-tracing-events"></a><span data-ttu-id="25a3c-139">작업 추적 이벤트만 기록하려면</span><span class="sxs-lookup"><span data-stu-id="25a3c-139">To log only activity tracing events</span></span>  
  
1.  <span data-ttu-id="25a3c-140">**솔루션 탐색기**에서 app.config를 마우스 오른쪽 단추로 클릭하고 **열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-140">Right-click app.config in the **Solution Explorer** and select **Open**.</span></span>  
  
     <span data-ttu-id="25a3c-141">또는</span><span class="sxs-lookup"><span data-stu-id="25a3c-141">-or-</span></span>  
  
     <span data-ttu-id="25a3c-142">app.config 파일이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="25a3c-142">If there is no app.config file:</span></span>  
  
    1.  <span data-ttu-id="25a3c-143">**프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-143">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="25a3c-144">**새 항목 추가** 대화 상자에서 **응용 프로그램 구성 파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-144">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="25a3c-145">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-145">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="25a3c-146">최상위 `<configuration>` 섹션의 `<system.diagnostics>` 섹션에 있는 `<switches>` 섹션으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-146">Locate the `<switches>` section, which is in the `<system.diagnostics>` section, which is in the top-level `<configuration>` section.</span></span>  
  
3.  <span data-ttu-id="25a3c-147">스위치 컬렉션에 `DefaultSwitch`를 추가하는 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-147">Find the element that adds `DefaultSwitch` to the collection of switches.</span></span> <span data-ttu-id="25a3c-148">이 요소는 다음과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-148">It should look similar to this element:</span></span>  
  
     `<add name="DefaultSwitch" value="Information" />`  
  
4.  <span data-ttu-id="25a3c-149">`value` 특성의 값을 "ActivityTracing"으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-149">Change the value of the `value` attribute to "ActivityTracing".</span></span>  
  
5.  <span data-ttu-id="25a3c-150">app.config 파일의 내용은 다음 XML과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-150">The content of the app.config file should be similar to the following XML:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <!-- This section configures My.Application.Log -->  
          <source name="DefaultSource" switchName="DefaultSwitch">  
            <listeners>  
              <add name="FileLog"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="DefaultSwitch" value="ActivityTracing" />  
        </switches>  
        <sharedListeners>  
          <add name="FileLog"  
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
                     Microsoft.VisualBasic, Version=8.0.0.0,   
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,   
                     processorArchitecture=MSIL"   
               initializeData="FileLogWriter"/>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
6.  <span data-ttu-id="25a3c-151">디버거에서 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-151">Run the application in the debugger.</span></span>  
  
7.  <span data-ttu-id="25a3c-152">**Button1**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-152">Press **Button1**.</span></span>  
  
     <span data-ttu-id="25a3c-153">응용 프로그램이 다음 정보를 응용 프로그램의 디버그 출력 및 로그 파일에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-153">The application writes the following information to the application's debug output and log file:</span></span>  
  
     `DefaultSource Start: 4 : Entering Button1_Click`  
  
     `DefaultSource Stop: 5 : Leaving Button1_Click`  
  
8.  <span data-ttu-id="25a3c-154">응용 프로그램을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-154">Close the application.</span></span>  
  
9. <span data-ttu-id="25a3c-155">`value` 특성의 값을 다시 "정보"로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-155">Change the value of the `value` attribute back to "Information".</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="25a3c-156">`DefaultSwitch` 스위치 설정은 `My.Application.Log`만 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-156">The `DefaultSwitch` switch setting controls only `My.Application.Log`.</span></span> <span data-ttu-id="25a3c-157">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.Diagnostics.Trace?displayProperty=nameWithType> 및 <xref:System.Diagnostics.Debug?displayProperty=nameWithType> 클래스의 동작은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-157">It does not change how the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.Diagnostics.Trace?displayProperty=nameWithType> and <xref:System.Diagnostics.Debug?displayProperty=nameWithType> classes behave.</span></span>  
  
## <a name="individual-filtering-for-myapplicationlog-listeners"></a><span data-ttu-id="25a3c-158">My.Application.Log 수신기에 대한 개별 필터링</span><span class="sxs-lookup"><span data-stu-id="25a3c-158">Individual Filtering For My.Application.Log Listeners</span></span>  
 <span data-ttu-id="25a3c-159">이전 예제에서는 모든 `My.Application.Log` 출력에 대한 필터링을 변경하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-159">The previous example shows how to change the filtering for all `My.Application.Log` output.</span></span> <span data-ttu-id="25a3c-160">이 예제에서는 개별 로그 수신기를 필터링하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-160">This example demonstrates how to filter an individual log listener.</span></span> <span data-ttu-id="25a3c-161">기본적으로 응용 프로그램에는 각각 응용 프로그램의 디버그 출력 및 로그 파일에 기록하는 두 개의 수신기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-161">By default, an application has two listeners that write to the application's debug output and the log file.</span></span>  
  
 <span data-ttu-id="25a3c-162">구성 파일은 각 로그 수신기에 `My.Application.Log`용 스위치와 비슷한 필터를 허용하여 로그 수신기의 동작을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-162">The configuration file controls the behavior of the log listeners by allowing each one to have a filter, which is similar to a switch for `My.Application.Log`.</span></span> <span data-ttu-id="25a3c-163">로그 수신기는 로그의 `DefaultSwitch` 및 로그 수신기의 필터에서 메시지의 심각도를 허용하는 경우에만 메시지를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-163">A log listener will output a message only if the message's severity is allowed by both the log's `DefaultSwitch` and the log listener's filter.</span></span>  
  
 <span data-ttu-id="25a3c-164">이 예제는 새 디버그 수신기에 대한 필터링을 구성하고 `Log` 개체에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-164">This example demonstrates how to configure filtering for a new debug listener and add it to the `Log` object.</span></span> <span data-ttu-id="25a3c-165">기본 디버그 수신기는 `Log` 개체에서 제거해야 하므로, 디버그 메시지가 새 디버그 수신기에서 오는 것이 분명합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-165">The default debug listener should be removed from the `Log` object, so it is clear that the debug messages come from the new debug listener.</span></span>  
  
#### <a name="to-log-only-activity-tracing-events"></a><span data-ttu-id="25a3c-166">동작 추적 이벤트만 기록하려면</span><span class="sxs-lookup"><span data-stu-id="25a3c-166">To log only activity-tracing events</span></span>  
  
1.  <span data-ttu-id="25a3c-167">**솔루션 탐색기**에서 app.config를 마우스 오른쪽 단추로 클릭하고 **열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-167">Right-click app.config in the **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="25a3c-168">또는</span><span class="sxs-lookup"><span data-stu-id="25a3c-168">-or-</span></span>  
  
     <span data-ttu-id="25a3c-169">app.config 파일이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="25a3c-169">If there is no app.config file:</span></span>  
  
    1.  <span data-ttu-id="25a3c-170">**프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-170">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="25a3c-171">**새 항목 추가** 대화 상자에서 **응용 프로그램 구성 파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-171">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="25a3c-172">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-172">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="25a3c-173">**솔루션 탐색기**에서 app.config를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-173">Right-click app.config in **Solution Explorer**.</span></span> <span data-ttu-id="25a3c-174">**열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-174">Choose **Open**.</span></span>  
  
3.  <span data-ttu-id="25a3c-175">`<sources>` 섹션 아래에서 `name` 특성이 "DefaultSource"인 `<source>` 섹션에서 `<listeners>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-175">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", which is under the `<sources>` section.</span></span> <span data-ttu-id="25a3c-176">`<sources>` 섹션은 최상위 `<configuration>` 섹션의 `<system.diagnostics>` 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-176">The `<sources>` section is under the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
4.  <span data-ttu-id="25a3c-177">이 요소를 `<listeners>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-177">Add this element to the `<listeners>` section:</span></span>  
  
    ```xml  
    <!-- Remove the default debug listener. -->  
    <remove name="Default"/>  
    <!-- Add a filterable debug listener. -->  
    <add name="NewDefault"/>  
    ```  
  
5.  <span data-ttu-id="25a3c-178">최상위 `<sharedListeners>` 섹션의 `<system.diagnostics>` 섹션에서 `<configuration>` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-178">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
6.  <span data-ttu-id="25a3c-179">다음 요소를 `<sharedListeners>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-179">Add this element to that `<sharedListeners>` section:</span></span>  
  
    ```xml  
    <add name="NewDefault"   
         type="System.Diagnostics.DefaultTraceListener,   
               System, Version=2.0.0.0, Culture=neutral,   
               PublicKeyToken=b77a5c561934e089,   
               processorArchitecture=MSIL">  
        <filter type="System.Diagnostics.EventTypeFilter"   
                initializeData="Error" />  
    </add>  
    ```  
  
     <span data-ttu-id="25a3c-180"><xref:System.Diagnostics.EventTypeFilter> 필터는 <xref:System.Diagnostics.SourceLevels> 열거형 값 중 하나를 해당 `initializeData` 특성으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-180">The <xref:System.Diagnostics.EventTypeFilter> filter takes one of the <xref:System.Diagnostics.SourceLevels> enumeration values as its `initializeData` attribute.</span></span>  
  
7.  <span data-ttu-id="25a3c-181">app.config 파일의 내용은 다음 XML과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-181">The content of the app.config file should be similar to the following XML:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <!-- This section configures My.Application.Log -->  
          <source name="DefaultSource" switchName="DefaultSwitch">  
            <listeners>  
              <add name="FileLog"/>  
              <!-- Remove the default debug listener. -->  
              <remove name="Default"/>  
              <!-- Add a filterable debug listener. -->  
              <add name="NewDefault"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="DefaultSwitch" value="Information" />  
        </switches>  
        <sharedListeners>  
          <add name="FileLog"  
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
                     Microsoft.VisualBasic, Version=8.0.0.0,   
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,   
                     processorArchitecture=MSIL"   
               initializeData="FileLogWriter"/>  
          <add name="NewDefault"   
               type="System.Diagnostics.DefaultTraceListener,   
                     System, Version=2.0.0.0, Culture=neutral,   
                     PublicKeyToken=b77a5c561934e089,   
                     processorArchitecture=MSIL">  
            <filter type="System.Diagnostics.EventTypeFilter"   
                    initializeData="Error" />  
          </add>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
8.  <span data-ttu-id="25a3c-182">디버거에서 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-182">Run the application in the debugger.</span></span>  
  
9. <span data-ttu-id="25a3c-183">**Button1**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-183">Press **Button1**.</span></span>  
  
     <span data-ttu-id="25a3c-184">응용 프로그램이 다음 정보를 응용 프로그램의 로그 파일에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-184">The application writes the following information to the application's log file:</span></span>  
  
     `Default Information: 0 : In Button1_Click`  
  
     `Default Error: 2 : Error in the application.`  
  
     <span data-ttu-id="25a3c-185">응용 프로그램은 좀 더 제한적인 필터링 때문에 응용 프로그램의 디버그 출력에 정보를 더 적게 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-185">The application writes less information to the application's debug output because of the more restrictive filtering.</span></span>  
  
     `Default Error   2   Error`  
  
10. <span data-ttu-id="25a3c-186">응용 프로그램을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="25a3c-186">Close the application.</span></span>  
  
 <span data-ttu-id="25a3c-187">배포 후 로그 설정을 변경하는 방법에 대한 자세한 내용은 [응용 프로그램 로그 작업](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25a3c-187">For more information about changing log settings after deployment, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25a3c-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25a3c-188">See Also</span></span>  
 [<span data-ttu-id="25a3c-189">연습: My.Application.Log가 정보를 기록하는 위치 확인</span><span class="sxs-lookup"><span data-stu-id="25a3c-189">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)  
 [<span data-ttu-id="25a3c-190">연습: My.Application.Log가 정보를 기록하는 위치 변경</span><span class="sxs-lookup"><span data-stu-id="25a3c-190">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)  
 [<span data-ttu-id="25a3c-191">연습: 사용자 지정 로그 수신기 만들기</span><span class="sxs-lookup"><span data-stu-id="25a3c-191">Walkthrough: Creating Custom Log Listeners</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)  
 [<span data-ttu-id="25a3c-192">방법: 로그 메시지 쓰기</span><span class="sxs-lookup"><span data-stu-id="25a3c-192">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)  
 [<span data-ttu-id="25a3c-193">추적 스위치</span><span class="sxs-lookup"><span data-stu-id="25a3c-193">Trace Switches</span></span>](../../../../framework/debug-trace-profile/trace-switches.md)  
 [<span data-ttu-id="25a3c-194">응용 프로그램의 정보 기록</span><span class="sxs-lookup"><span data-stu-id="25a3c-194">Logging Information from the Application</span></span>](../../../../visual-basic/developing-apps/programming/log-info/logging-information-from-the-application.md)
