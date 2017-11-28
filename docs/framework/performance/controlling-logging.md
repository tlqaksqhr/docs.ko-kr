---
title: ".NET Framework 로깅 제어"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: CLR ETW events, logging
ms.assetid: ce13088e-3095-4f0e-9f6b-fad30bbd3d41
caps.latest.revision: "40"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f996cf730acc355f3bf13287b79581d23e4e6a5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="controlling-net-framework-logging"></a><span data-ttu-id="56f23-102">.NET Framework 로깅 제어</span><span class="sxs-lookup"><span data-stu-id="56f23-102">Controlling .NET Framework Logging</span></span>
<span data-ttu-id="56f23-103">ETW(Windows용 이벤트 추적)를 사용하여 CLR(공용 언어 런타임) 이벤트를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-103">You can use event tracing for Windows (ETW) to record common language runtime (CLR) events.</span></span> <span data-ttu-id="56f23-104">다음과 같은 도구를 사용하여 추적을 만들고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-104">You can create and view traces by using the following tools:</span></span>  
  
-   <span data-ttu-id="56f23-105">Windows 운영 체제에 포함되어 있는 [Logman](http://go.microsoft.com/fwlink/?LinkId=150916) 및 [Tracerpt](http://go.microsoft.com/fwlink/?LinkId=150919) 명령줄 도구</span><span class="sxs-lookup"><span data-stu-id="56f23-105">The [Logman](http://go.microsoft.com/fwlink/?LinkId=150916) and [Tracerpt](http://go.microsoft.com/fwlink/?LinkId=150919) command-line tools, which are included with the Windows operating system.</span></span>  
  
-   <span data-ttu-id="56f23-106">[Windows 성능 도구 키트](http://msdn.microsoft.com/library/windows/hardware/hh162945.aspx)에 있는 [Xperf](http://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) 도구</span><span class="sxs-lookup"><span data-stu-id="56f23-106">The [Xperf](http://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) tools in the [Windows Performance Toolkit](http://msdn.microsoft.com/library/windows/hardware/hh162945.aspx).</span></span> <span data-ttu-id="56f23-107">Xperf에 대한 자세한 내용은 [Windows Performance 블로그](http://go.microsoft.com/fwlink/?LinkId=179509)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56f23-107">For more information about Xperf, see the [Windows Performance blog](http://go.microsoft.com/fwlink/?LinkId=179509).</span></span>  
  
 <span data-ttu-id="56f23-108">CLR 이벤트 정보를 캡처하려면 컴퓨터에 CLR 공급자가 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-108">To capture CLR event information, the CLR provider must be installed on your computer.</span></span> <span data-ttu-id="56f23-109">공급자가 설치되어 있는지 확인하려면 명령줄에 `logman query providers`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-109">To confirm that the provider is installed, type `logman query providers` at the command prompt.</span></span> <span data-ttu-id="56f23-110">공급자 목록이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-110">A list of providers is displayed.</span></span> <span data-ttu-id="56f23-111">이 목록에는 다음과 같이 CLR 공급자 항목이 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-111">This list should contain an entry for the CLR provider, as follows.</span></span>  
  
```  
Provider                                 GUID  
-------------------------------------------------------------------------------  
.NET Common Language Runtime    {E13C0D23-CCBC-4E12-931B-D9CC2EEE27E4}.  
```  
  
 <span data-ttu-id="56f23-112">CLR 공급자가 목록에 없는 경우 Windows [Wevtutil](http://go.microsoft.com/fwlink/?LinkID=150915) 명령줄 도구를 사용하여 Windows Vista 이상의 운영 체제에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-112">If the CLR provider is not listed, you can install it on Windows Vista and later operating systems by using the Windows [Wevtutil](http://go.microsoft.com/fwlink/?LinkID=150915) command-line tool.</span></span> <span data-ttu-id="56f23-113">관리자 권한으로 명령 프롬프트 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-113">Open the Command Prompt window as an administrator.</span></span> <span data-ttu-id="56f23-114">프롬프트 디렉터리를 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 폴더(%WINDIR%\Microsoft.NET\Framework[64]\v4.\<.NET 버전>\)로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-114">Change the prompt directory to the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] folder (%WINDIR%\Microsoft.NET\Framework[64]\v4.\<.NET version>\ ).</span></span> <span data-ttu-id="56f23-115">이 폴더에는 CLR-ETW.man 파일이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-115">This folder contains the CLR-ETW.man file.</span></span> <span data-ttu-id="56f23-116">명령 프롬프트에서 다음 명령을 입력하여 CLR 공급자를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-116">At the command prompt, type the following command to install the CLR provider:</span></span>  
  
 `wevtutil im CLR-ETW.man`  
  
## <a name="capturing-clr-etw-events"></a><span data-ttu-id="56f23-117">CLR ETW 이벤트 캡처</span><span class="sxs-lookup"><span data-stu-id="56f23-117">Capturing CLR ETW Events</span></span>  
 <span data-ttu-id="56f23-118">[Logman](http://go.microsoft.com/fwlink/?LinkId=150916) 및 [Xperf](http://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) 명령줄 도구를 사용하여 ETW 이벤트를 캡처하고, [Tracerpt](http://go.microsoft.com/fwlink/?LinkId=150919) 및 [Xperf](http://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) 도구를 사용하여 추적 이벤트를 디코딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-118">You can use the [Logman](http://go.microsoft.com/fwlink/?LinkId=150916) and [Xperf](http://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) command-line tools to capture ETW events, and the [Tracerpt](http://go.microsoft.com/fwlink/?LinkId=150919) and [Xperf](http://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) tools to decode the trace events.</span></span>  
  
 <span data-ttu-id="56f23-119">로깅을 설정하려면 사용자가 다음 세 가지를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-119">To turn on logging, a user must specify three things:</span></span>  
  
-   <span data-ttu-id="56f23-120">통신 대상 공급자</span><span class="sxs-lookup"><span data-stu-id="56f23-120">The provider to communicate to.</span></span>  
  
-   <span data-ttu-id="56f23-121">일련의 키워드를 나타내는 64비트 숫자.</span><span class="sxs-lookup"><span data-stu-id="56f23-121">A 64-bit number that represents a set of keywords.</span></span> <span data-ttu-id="56f23-122">각 키워드는 공급자가 설정할 수 있는 이벤트 집합을 나타내고,</span><span class="sxs-lookup"><span data-stu-id="56f23-122">Each keyword represents a set of events that the provider can turn on.</span></span> <span data-ttu-id="56f23-123">숫자는 설정할 키워드가 결합된 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-123">The number represents a combined set of keywords to turn on.</span></span>  
  
-   <span data-ttu-id="56f23-124">로그 수준(자세한 정도)을 나타내는 작은 숫자.</span><span class="sxs-lookup"><span data-stu-id="56f23-124">A small number representing the level (verbosity) to log at.</span></span> <span data-ttu-id="56f23-125">수준 1은 가장 간결하고 수준 5는 가장 자세합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-125">Level 1 is the least verbose, and level 5 is the most verbose.</span></span> <span data-ttu-id="56f23-126">기본값은 수준 0이고, 이 수준은 공급자별로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-126">Level 0 is a default whose meaning is provider-specific.</span></span>  
  
#### <a name="to-capture-clr-etw-events-using-logman"></a><span data-ttu-id="56f23-127">Logman을 사용하여 CLR ETW 이벤트를 캡처하려면</span><span class="sxs-lookup"><span data-stu-id="56f23-127">To capture CLR ETW events using Logman</span></span>  
  
1.  <span data-ttu-id="56f23-128">명령 프롬프트에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-128">At the command prompt, type:</span></span>  
  
     `logman start clrevents -p {e13c0d23-ccbc-4e12-931b-d9cc2eee27e4} 0x1CCBD 0x5 -ets -ct perf`  
  
     <span data-ttu-id="56f23-129">여기서</span><span class="sxs-lookup"><span data-stu-id="56f23-129">where:</span></span>  
  
    -   <span data-ttu-id="56f23-130">`-p` 매개 변수는 공급자 GUID를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-130">The `-p` parameter identifies the provider GUID.</span></span>  
  
    -   <span data-ttu-id="56f23-131">`0x1CCBD`는 발생할 이벤트의 범주를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-131">`0x1CCBD` specifies the categories of events that will be raised.</span></span>  
  
    -   <span data-ttu-id="56f23-132">`0x5`는 로깅 수준을 설정합니다(이 경우, verbose(5)).</span><span class="sxs-lookup"><span data-stu-id="56f23-132">`0x5` sets the level of logging (in this case, verbose (5)).</span></span>  
  
    -   <span data-ttu-id="56f23-133">`-ets` 매개 변수는 이벤트 추적 세션에 명령을 보내도록 Logman에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-133">The `-ets` parameter instructs Logman to send commands to event tracing sessions.</span></span>  
  
    -   <span data-ttu-id="56f23-134">`-ct perf` 매개 변수는 `QueryPerformanceCounter` 함수를 사용하여 각 이벤트의 타임 스탬프를 로깅할 것임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-134">The `-ct perf` parameter specifies that the `QueryPerformanceCounter` function will be used to log the time stamp for each event.</span></span>  
  
2.  <span data-ttu-id="56f23-135">이벤트 로깅을 중지하려면 다음을 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="56f23-135">To stop logging the events, type:</span></span>  
  
     `logman stop clrevents -ets`  
  
     <span data-ttu-id="56f23-136">이 명령은 clrevents.etl이라는 이진 추적 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-136">This command creates a binary trace file named clrevents.etl.</span></span>  
  
#### <a name="to-capture-clr-etw-events-using-xperf"></a><span data-ttu-id="56f23-137">Xperf를 사용하여 CLR ETW 이벤트를 캡처하려면</span><span class="sxs-lookup"><span data-stu-id="56f23-137">To capture CLR ETW events using Xperf</span></span>  
  
1.  <span data-ttu-id="56f23-138">명령 프롬프트에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-138">At the command prompt, type:</span></span>  
  
     `xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:5 -f clrevents.etl`  
  
     <span data-ttu-id="56f23-139">여기서 GUID는 CLR ETW 공급자 GUID이고, `0x1CCBD:5`는 수준 5(verbose) 이하의 모든 내용을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-139">where the GUID is the CLR ETW provider GUID, and `0x1CCBD:5` traces everything at and below level 5 (verbose).</span></span>  
  
2.  <span data-ttu-id="56f23-140">추적을 중지하려면 다음을 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="56f23-140">To stop tracing, type:</span></span>  
  
     `Xperf -stop clr`  
  
     <span data-ttu-id="56f23-141">이 명령은 clrevents.etl이라는 추적 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-141">This command creates a trace file named clrevents.etl.</span></span>  
  
## <a name="viewing-clr-etw-events"></a><span data-ttu-id="56f23-142">CLR ETW 이벤트 보기</span><span class="sxs-lookup"><span data-stu-id="56f23-142">Viewing CLR ETW Events</span></span>  
 <span data-ttu-id="56f23-143">아래의 명령을 사용하여 CLR ETW 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-143">Use the commands listed below to view the CLR ETW events.</span></span> <span data-ttu-id="56f23-144">이벤트에 대한 설명은 [CLR ETW 이벤트](../../../docs/framework/performance/clr-etw-events.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56f23-144">For a description of the events, see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md).</span></span>  
  
#### <a name="to-view-clr-etw-events-using-tracerpt"></a><span data-ttu-id="56f23-145">Tracerpt를 사용하여 CLR ETW 이벤트를 보려면</span><span class="sxs-lookup"><span data-stu-id="56f23-145">To view CLR ETW events using Tracerpt</span></span>  
  
-   <span data-ttu-id="56f23-146">명령 프롬프트에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-146">At the command prompt, type:</span></span>  
  
     `tracerpt clrevents.etl`  
  
     <span data-ttu-id="56f23-147">이 명령은 dumpfile.xml 및 summary.txt라는 두 개의 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-147">This command creates two files: dumpfile.xml and summary.txt.</span></span> <span data-ttu-id="56f23-148">dumpfile.xml 파일은 모든 이벤트를 나열하고, summary.txt는 이벤트 요약을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-148">The dumpfile.xml file lists all the events, and summary.txt provides a summary of the events.</span></span>  
  
#### <a name="to-view-clr-etw-events-using-xperf"></a><span data-ttu-id="56f23-149">Xperf를 사용하여 CLR ETW 이벤트를 보려면</span><span class="sxs-lookup"><span data-stu-id="56f23-149">To view CLR ETW events using Xperf</span></span>  
  
-   <span data-ttu-id="56f23-150">명령 프롬프트에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-150">At the command prompt, type:</span></span>  
  
     `xperf clrevents.etl`  
  
     <span data-ttu-id="56f23-151">이 명령은 Xperf ETL 파일 뷰어를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-151">This command opens the Xperf ETL file viewer.</span></span> <span data-ttu-id="56f23-152">이 뷰어에서 CLR 이벤트는 **제네릭 이벤트** 뷰에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-152">In this viewer, the CLR events show up in the **Generic Events** view.</span></span> <span data-ttu-id="56f23-153">유형별로 범주화된 이벤트의 데이터 표를 표시하려면 이 뷰에서 시간 영역을 선택한 다음 마우스 오른쪽 단추를 클릭하고 **요약**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-153">To display a data grid of events categorized by type, select a region of time in this view, and then right-click and select **Summary**.</span></span>  
  
#### <a name="to-convert-the-etl-file-to-a-comma-separated-value-file"></a><span data-ttu-id="56f23-154">.etl 파일을 쉼표로 구분된 값 파일로 변환하려면</span><span class="sxs-lookup"><span data-stu-id="56f23-154">To convert the .etl file to a comma-separated value file</span></span>  
  
-   <span data-ttu-id="56f23-155">명령 프롬프트에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-155">At the command prompt, type:</span></span>  
  
     `xperf -i clrevents.etl -f clrevents.csv`  
  
     <span data-ttu-id="56f23-156">이 명령에 의해 XPerf는 사용자가 볼 수 있는 쉼표로 분리된 값 파일(CSV)로 이벤트를 덤프하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-156">This command causes XPerf to dump the events as a comma separated value (CSV) file that you can view.</span></span> <span data-ttu-id="56f23-157">이벤트별로 서로 다른 필드가 있기 때문에 이 CSV 파일에서는 데이터 앞에 헤더 줄이 둘 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-157">Because different events have different fields, this CSV file is contains more than one header line before the data.</span></span> <span data-ttu-id="56f23-158">모든 줄의 첫 번째 필드는 이벤트 유형이고, 이 유형은 나머지 필드 확인에 사용되어야 하는 헤더를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="56f23-158">The first field of every line is the event type, which indicates which header should be used to determine the rest of the fields.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f23-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56f23-159">See Also</span></span>  
 [<span data-ttu-id="56f23-160">Windows Performance Toolkit</span><span class="sxs-lookup"><span data-stu-id="56f23-160">Windows Performance Toolkit</span></span>](http://go.microsoft.com/fwlink/?LinkID=161141)  
 [<span data-ttu-id="56f23-161">공용 언어 런타임의 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="56f23-161">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
