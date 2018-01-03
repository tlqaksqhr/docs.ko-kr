---
title: "추적 스위치"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework], trace switches
- trace switches, about trace switches
- tracing [.NET Framework], level of detail
- switches, trace
- trace switches
- trace switches, creating custom
ms.assetid: 8ab913aa-f400-4406-9436-f45bc6e54fbe
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4df092afd4d60811683b4187df78f27ad971cf89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="trace-switches"></a><span data-ttu-id="60421-102">추적 스위치</span><span class="sxs-lookup"><span data-stu-id="60421-102">Trace Switches</span></span>
<span data-ttu-id="60421-103">추적 스위치를 사용하여 추적 출력을 활성화, 비활성화 및 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60421-103">Trace switches enable you to enable, disable, and filter tracing output.</span></span> <span data-ttu-id="60421-104">코드에 존재하며 .config 파일을 통해 외부에서 구성할 수 있는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="60421-104">They are objects that exist in your code and can be configured externally through the .config file.</span></span> <span data-ttu-id="60421-105">.NET Framework에서 제공되는 세 가지 유형의 추적 스위치( <xref:System.Diagnostics.BooleanSwitch> 클래스, <xref:System.Diagnostics.TraceSwitch> 클래스 및 <xref:System.Diagnostics.SourceSwitch> 클래스)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60421-105">There are three types of trace switches provided in the .NET Framework: the <xref:System.Diagnostics.BooleanSwitch> class, the <xref:System.Diagnostics.TraceSwitch> class, and the <xref:System.Diagnostics.SourceSwitch> class.</span></span> <span data-ttu-id="60421-106"><xref:System.Diagnostics.BooleanSwitch> 클래스는 다양한 trace 문을 사용하거나 사용하지 않도록 설정하는 토글 스위치 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="60421-106">The <xref:System.Diagnostics.BooleanSwitch> class acts as a toggle switch, either enabling or disabling a variety of trace statements.</span></span> <span data-ttu-id="60421-107"><xref:System.Diagnostics.TraceSwitch> 및 <xref:System.Diagnostics.SourceSwitch> 클래스를 통해 특정 추적 수준에 대한 추적 스위치를 사용하도록 설정하여 해당 수준 및 그 아래의 모든 수준에 대해 지정된 <xref:System.Diagnostics.Trace> 또는 <xref:System.Diagnostics.TraceSource> 메시지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60421-107">The <xref:System.Diagnostics.TraceSwitch> and <xref:System.Diagnostics.SourceSwitch> classes allow you to enable a trace switch for a particular tracing level so that the <xref:System.Diagnostics.Trace> or <xref:System.Diagnostics.TraceSource> messages specified for that level and all levels below it appear.</span></span> <span data-ttu-id="60421-108">스위치를 사용하지 않도록 설정하면 추적 메시지가 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60421-108">If you disable the switch, the trace messages will not appear.</span></span> <span data-ttu-id="60421-109">이러한 모든 클래스는 사용자 개발 스위치와 마찬가지로 추상(**MustInherit**) 클래스 **Switch**에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="60421-109">All these classes derive from the abstract (**MustInherit**) class **Switch**, as should any user-developed switches.</span></span>  
  
 <span data-ttu-id="60421-110">추적 스위치는 정보를 필터링하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60421-110">Trace switches can be useful for filtering information.</span></span> <span data-ttu-id="60421-111">예를 들어 데이터 액세스 모듈에서는 모든 추적 메시지가 표시되고 응용 프로그램의 나머지 부분에서는 오류 메시지만 표시되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60421-111">For example, you might want to see every tracing message in a data access module, but only error messages in the rest of the application.</span></span> <span data-ttu-id="60421-112">이 경우 데이터 액세스 모듈에 대해 하나의 추적 스위치를 사용하고 응용 프로그램의 나머지 부분에 대해 하나의 스위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="60421-112">In that case, you would use one trace switch for the data access module and one switch for the rest of the application.</span></span> <span data-ttu-id="60421-113">.config 파일을 사용하여 스위치를 적절한 설정으로 구성하면 수신하는 추적 메시지 유형을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60421-113">By using the .config file to configure the switches to the appropriate settings, you could control what types of trace message you received.</span></span> <span data-ttu-id="60421-114">자세한 내용은 [방법: 추적 스위치 만들기, 초기화 및 구성](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60421-114">For more information, see [How to: Create, Initialize and Configure Trace Switches](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md).</span></span>  
  
 <span data-ttu-id="60421-115">일반적으로 배포된 응용 프로그램은 응용 프로그램 실행 시 화면에 나타나거나 로그 파일에 채워지는 여러 관련 없는 추적 메시지를 사용자가 관찰할 필요가 없도록 스위치를 사용할 수 없는 상태로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="60421-115">Typically, a deployed application is executed with its switches disabled, so that users need not observe a lot of irrelevant trace messages appearing on a screen or filling up a log file as the application runs.</span></span> <span data-ttu-id="60421-116">응용 프로그램 실행 중에 문제가 발생할 경우 응용 프로그램을 중지하고 스위치를 사용하도록 설정한 다음 응용 프로그램을 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60421-116">If a problem arises during application execution, you can stop the application, enable the switches, and restart the application.</span></span> <span data-ttu-id="60421-117">그러면 추적 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="60421-117">Then the tracing messages will be displayed.</span></span>  
  
 <span data-ttu-id="60421-118">스위치를 사용하려면 먼저 **BooleanSwitch** 클래스, **TraceSwitch** 클래스 또는 개발자 정의 스위치 클래스에서 스위치 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60421-118">To use a switch you must first create a switch object from a **BooleanSwitch** class, a **TraceSwitch** class, or a developer-defined switch class.</span></span> <span data-ttu-id="60421-119">개발자 정의 스위치를 만드는 방법에 대한 자세한 내용은 .NET Framework 참조에서 <xref:System.Diagnostics.Switch> 클래스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60421-119">For more information about creating developer-defined switches, see the <xref:System.Diagnostics.Switch> class in the .NET Framework reference.</span></span> <span data-ttu-id="60421-120">스위치 개체를 사용할 시기를 지정하는 구성 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="60421-120">Then you set a configuration value that specifies when the switch object is to be used.</span></span> <span data-ttu-id="60421-121">그런 후에 다양한 **추적** (또는 **디버그**) 추적 메서드에서 스위치 개체의 설정을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="60421-121">You then test the setting of the switch object in various **Trace** (or **Debug**) tracing methods.</span></span>  
  
## <a name="trace-levels"></a><span data-ttu-id="60421-122">추적 수준</span><span class="sxs-lookup"><span data-stu-id="60421-122">Trace Levels</span></span>  
 <span data-ttu-id="60421-123">**TraceSwitch**를 사용하는 경우 추가로 고려해야 할 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60421-123">When you use **TraceSwitch**, there are additional considerations.</span></span> <span data-ttu-id="60421-124">**TraceSwitch** 개체에는 스위치가 특정 수준 이상으로 설정되었는지 여부를 나타내는 **부울** 값을 반환하는 다음 4가지 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60421-124">A **TraceSwitch** object has four properties that return **Boolean** values indicating whether the switch is set to at least a particular level:</span></span>  
  
-   <xref:System.Diagnostics.TraceSwitch.TraceError%2A?displayProperty=nameWithType>  
  
-   <xref:System.Diagnostics.TraceSwitch.TraceWarning%2A?displayProperty=nameWithType>  
  
-   <xref:System.Diagnostics.TraceSwitch.TraceInfo%2A?displayProperty=nameWithType>  
  
-   <xref:System.Diagnostics.TraceSwitch.TraceVerbose%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="60421-125">수준을 통해 수신하는 추적 정보의 양을 문제 해결에 필요한 정보로만 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60421-125">Levels allow you to limit the amount of tracing information you receive to only that information needed to solve a problem.</span></span> <span data-ttu-id="60421-126">추적 스위치를 적절한 추적 수준으로 설정하고 구성하여 추적 출력에 표시할 세부 정보 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="60421-126">You specify the level of detail you want in your tracing output by setting and configuring trace switches to the appropriate trace level.</span></span> <span data-ttu-id="60421-127">오류 메시지, 경고 메시지, 정보 메시지, 자세한 추적 메시지를 수신하거나 메시지를 수신하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60421-127">You can receive error messages, warning messages, informational messages, verbose tracing messages, or no message at all.</span></span>  
  
 <span data-ttu-id="60421-128">각 수준에 연결할 메시지 종류는 전적으로 사용자가 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="60421-128">It is entirely up to you to decide what kind of message to associate with each level.</span></span> <span data-ttu-id="60421-129">일반적으로 추적 메시지의 내용은 각 수준에 연결하는 항목에 따라 달라지지만 수준 간의 차이를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="60421-129">Typically, the content of tracing messages depends on what you associate with each level, but you determine the differences between levels.</span></span> <span data-ttu-id="60421-130">예를 들어 수준 3(**Info**)에서는 문제에 대한 자세한 설명을 제공하지만 수준 1(**Error**)에서는 오류 참조 번호만 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60421-130">You might want to provide detailed descriptions of a problem at level 3 (**Info**), for example, but provide only an error reference number at level 1 (**Error**).</span></span> <span data-ttu-id="60421-131">응용 프로그램에 가장 적합한 체계는 전적으로 사용자가 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="60421-131">It is entirely up to you to decide what scheme works best in your application.</span></span>  
  
 <span data-ttu-id="60421-132">이러한 속성은 **TraceLevel** 열거형의 값 1-4에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="60421-132">These properties correspond to the values 1 through 4 of the **TraceLevel** enumeration.</span></span> <span data-ttu-id="60421-133">다음 표에서는 **TraceLevel** 열거형의 수준 및 해당 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="60421-133">The following table lists the levels of the **TraceLevel** enumeration and their values.</span></span>  
  
|<span data-ttu-id="60421-134">열거형 값</span><span class="sxs-lookup"><span data-stu-id="60421-134">Enumerated value</span></span>|<span data-ttu-id="60421-135">정수 값</span><span class="sxs-lookup"><span data-stu-id="60421-135">Integer value</span></span>|<span data-ttu-id="60421-136">표시(또는 지정된 출력 대상에 기록)되는 메시지 유형</span><span class="sxs-lookup"><span data-stu-id="60421-136">Type of message displayed (or written to a specified output target)</span></span>|  
|----------------------|-------------------|---------------------------------------------------------------------------|  
|<span data-ttu-id="60421-137">끄기</span><span class="sxs-lookup"><span data-stu-id="60421-137">Off</span></span>|<span data-ttu-id="60421-138">0</span><span class="sxs-lookup"><span data-stu-id="60421-138">0</span></span>|<span data-ttu-id="60421-139">없음</span><span class="sxs-lookup"><span data-stu-id="60421-139">None</span></span>|  
|<span data-ttu-id="60421-140">Error</span><span class="sxs-lookup"><span data-stu-id="60421-140">Error</span></span>|<span data-ttu-id="60421-141">1</span><span class="sxs-lookup"><span data-stu-id="60421-141">1</span></span>|<span data-ttu-id="60421-142">오류 메시지만</span><span class="sxs-lookup"><span data-stu-id="60421-142">Only error messages</span></span>|  
|<span data-ttu-id="60421-143">경고</span><span class="sxs-lookup"><span data-stu-id="60421-143">Warning</span></span>|<span data-ttu-id="60421-144">2</span><span class="sxs-lookup"><span data-stu-id="60421-144">2</span></span>|<span data-ttu-id="60421-145">경고 메시지와 오류 메시지</span><span class="sxs-lookup"><span data-stu-id="60421-145">Warning messages and error messages</span></span>|  
|<span data-ttu-id="60421-146">Info</span><span class="sxs-lookup"><span data-stu-id="60421-146">Info</span></span>|<span data-ttu-id="60421-147">3</span><span class="sxs-lookup"><span data-stu-id="60421-147">3</span></span>|<span data-ttu-id="60421-148">정보 메시지, 경고 메시지 및 오류 메시지</span><span class="sxs-lookup"><span data-stu-id="60421-148">Informational messages, warning messages, and error messages</span></span>|  
|<span data-ttu-id="60421-149">자세히</span><span class="sxs-lookup"><span data-stu-id="60421-149">Verbose</span></span>|<span data-ttu-id="60421-150">4</span><span class="sxs-lookup"><span data-stu-id="60421-150">4</span></span>|<span data-ttu-id="60421-151">자세한 메시지, 정보 메시지, 경고 메시지 및 오류 메시지</span><span class="sxs-lookup"><span data-stu-id="60421-151">Verbose messages, informational messages, warning messages, and error messages</span></span>|  
  
 <span data-ttu-id="60421-152">**TraceSwitch** 속성은 스위치에 대한 최대 추적 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="60421-152">The **TraceSwitch** properties indicate the maximum trace level for the switch.</span></span> <span data-ttu-id="60421-153">즉, 지정된 수준 및 모든 하위 수준에 대한 추적 정보가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="60421-153">That is, tracing information is written for the level specified as well as for all lower levels.</span></span> <span data-ttu-id="60421-154">예를 들어 **TraceInfo** 가 **true**이면 **TraceError** 및 **TraceWarning** 도 **true** 이지만 **TraceVerbose** 는 **false**가 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60421-154">For example, if **TraceInfo** is **true**, then **TraceError** and **TraceWarning** are also **true** but **TraceVerbose** might well be **false**.</span></span>  
  
 <span data-ttu-id="60421-155">이러한 속성은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="60421-155">These properties are read-only.</span></span> <span data-ttu-id="60421-156">**TraceLevel** 속성이 설정될 때 **TraceSwitch** 개체가 자동으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="60421-156">The **TraceSwitch** object automatically sets them when the **TraceLevel** property is set.</span></span> <span data-ttu-id="60421-157">예:</span><span class="sxs-lookup"><span data-stu-id="60421-157">For example:</span></span>  
  
```vb  
Dim myTraceSwitch As New TraceSwitch("SwitchOne", "The first switch")  
myTraceSwitch.Level = TraceLevel.Info  
' This message box displays true, because setting the level to  
' TraceLevel.Info sets all lower levels to true as well.  
MessageBox.Show(myTraceSwitch.TraceWarning.ToString())  
' This messagebox displays false.  
MessageBox.Show(myTraceSwitch.TraceVerbose.ToString())  
```  
  
```csharp  
System.Diagnostics.TraceSwitch myTraceSwitch =   
   new System.Diagnostics.TraceSwitch("SwitchOne", "The first switch");  
myTraceSwitch.Level = System.Diagnostics.TraceLevel.Info;  
// This message box displays true, because setting the level to   
// TraceLevel.Info sets all lower levels to true as well.  
MessageBox.Show(myTraceSwitch.TraceWarning.ToString());  
// This message box displays false.  
MessageBox.Show(myTraceSwitch.TraceVerbose.ToString());  
```  
  
## <a name="developer-defined-switches"></a><span data-ttu-id="60421-158">개발자 정의 스위치</span><span class="sxs-lookup"><span data-stu-id="60421-158">Developer-Defined Switches</span></span>  
 <span data-ttu-id="60421-159">**BooleanSwitch** 및 **TraceSwitch**를 제공하는 것 외에도 **Switch** 클래스에서 상속하고 기본 클래스 메서드를 사용자 지정 메서드로 재정의하여 고유한 스위치를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60421-159">In addition to providing **BooleanSwitch** and **TraceSwitch**, you can define your own switches by inheriting from the **Switch** class and overriding the base class methods with customized methods.</span></span> <span data-ttu-id="60421-160">개발자 정의 스위치를 만드는 방법에 대한 자세한 내용은 .NET Framework 참조에서 <xref:System.Diagnostics.Switch> 클래스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60421-160">For more information about creating developer-defined switches, see the <xref:System.Diagnostics.Switch> class in the .NET Framework reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60421-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60421-161">See Also</span></span>  
 [<span data-ttu-id="60421-162">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="60421-162">Trace Listeners</span></span>](../../../docs/framework/debug-trace-profile/trace-listeners.md)  
 [<span data-ttu-id="60421-163">방법: 응용 프로그램 코드에 Trace 문 추가</span><span class="sxs-lookup"><span data-stu-id="60421-163">How to: Add Trace Statements to Application Code</span></span>](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)  
 [<span data-ttu-id="60421-164">응용 프로그램 추적 및 조율</span><span class="sxs-lookup"><span data-stu-id="60421-164">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
