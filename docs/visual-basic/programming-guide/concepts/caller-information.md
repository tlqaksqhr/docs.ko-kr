---
title: "호출자 정보 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 15d556eb-4d0c-4497-98a3-7f60abb7d6a1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dfd9339e990b2a2a7c57acde3c91295a7154fdc0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="caller-information-visual-basic"></a><span data-ttu-id="95d38-102">호출자 정보 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95d38-102">Caller Information (Visual Basic)</span></span>
<span data-ttu-id="95d38-103">호출자 정보 특성을 사용하여 메서드 호출자에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-103">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="95d38-104">소스 코드 파일 경로, 소스 코드 줄 번호 및 호출자의 멤버 이름을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-104">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="95d38-105">이 정보는 추적, 디버깅 및 진단 도구를 만드는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-105">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>  
  
 <span data-ttu-id="95d38-106">이 정보를 얻으려면 각각 기본값이 있는 선택적 매개 변수에 적용되는 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-106">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="95d38-107">다음 표에서는 <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> 네임스페이스에 정의된 호출자 정보 특성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-107">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>  
  
|<span data-ttu-id="95d38-108">특성</span><span class="sxs-lookup"><span data-stu-id="95d38-108">Attribute</span></span>|<span data-ttu-id="95d38-109">설명</span><span class="sxs-lookup"><span data-stu-id="95d38-109">Description</span></span>|<span data-ttu-id="95d38-110">형식</span><span class="sxs-lookup"><span data-stu-id="95d38-110">Type</span></span>|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="95d38-111">호출자를 포함한 소스 파일의 전체 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-111">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="95d38-112">컴파일 시간의 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-112">This is the file path at compile time.</span></span>|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="95d38-113">메서드가 호출되는 소스 파일의 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-113">Line number in the source file at which the method is called.</span></span>|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="95d38-114">호출자의 메서드 또는 속성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-114">Method or property name of the caller.</span></span> <span data-ttu-id="95d38-115">이 항목의 뒷부분에 있는 [멤버 이름](#MEMBERNAMES)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95d38-115">See [Member Names](#MEMBERNAMES) later in this topic.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="95d38-116">예제</span><span class="sxs-lookup"><span data-stu-id="95d38-116">Example</span></span>  
 <span data-ttu-id="95d38-117">다음 예제에서는 호출자 정보 특성을 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-117">The following example shows how to use Caller Info attributes.</span></span> <span data-ttu-id="95d38-118">`TraceMessage` 메서드에 대한 각 호출에서 호출자 정보는 선택적 매개 변수에 대한 인수로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-118">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>  
  
```vb  
Private Sub DoProcessing()  
    TraceMessage("Something happened.")  
End Sub  
  
Public Sub TraceMessage(message As String,  
        <System.Runtime.CompilerServices.CallerMemberName> Optional memberName As String = Nothing,  
        <System.Runtime.CompilerServices.CallerFilePath> Optional sourcefilePath As String = Nothing,  
        <System.Runtime.CompilerServices.CallerLineNumber()> Optional sourceLineNumber As Integer = 0)  
  
    System.Diagnostics.Trace.WriteLine("message: " & message)  
    System.Diagnostics.Trace.WriteLine("member name: " & memberName)  
    System.Diagnostics.Trace.WriteLine("source file path: " & sourcefilePath)  
    System.Diagnostics.Trace.WriteLine("source line number: " & sourceLineNumber)  
End Sub  
  
' Sample output:  
'   message: Something happened.  
'   member name: DoProcessing  
'   source file path: C:\Users\username\Documents\Visual Studio 2012\Projects\CallerInfoVB\CallerInfoVB\Form1.vb  
'   source line number: 15  
```  
  
## <a name="remarks"></a><span data-ttu-id="95d38-119">주의</span><span class="sxs-lookup"><span data-stu-id="95d38-119">Remarks</span></span>  
 <span data-ttu-id="95d38-120">각각의 선택적 매개 변수에 대한 명시적 기본값을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-120">You must specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="95d38-121">선택적으로 지정되지 않은 매개 변수에 호출자 정보 특성을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-121">You can't apply Caller Info attributes to parameters that aren't specified as optional.</span></span>  
  
 <span data-ttu-id="95d38-122">호출자 정보 특성은 매개 변수를 선택적 매개 변수로 만들지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-122">The Caller Info attributes don't make a parameter optional.</span></span> <span data-ttu-id="95d38-123">대신, 이런 특성은 인수가 생략될 때 전달되는 기본값에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-123">Instead, they affect the default value that's passed in when the argument is omitted.</span></span>  
  
 <span data-ttu-id="95d38-124">호출자 정보 값은 컴파일 시간에 리터럴로 중간 언어(IL) 내로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-124">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="95d38-125">예외에 대한 <xref:System.Exception.StackTrace%2A> 속성의 결과와 달리 결과가 난독화의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-125">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span>  
  
 <span data-ttu-id="95d38-126">선택적 인수를 명시적으로 제공하여 호출자 정보를 제어하거나 호출자 정보를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-126">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>  
  
###  <a name="MEMBERNAMES"></a> <span data-ttu-id="95d38-127">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="95d38-127">Member Names</span></span>  
 <span data-ttu-id="95d38-128">`CallerMemberName` 특성을 사용하여 멤버 이름을 호출된 메서드에 대한 `String` 인수로 지정하는 것을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-128">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="95d38-129">이 기술을 사용하여 **이름 바꾸기 리팩터링**이 `String` 값을 변경하지 못하는 문제를 피합니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-129">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="95d38-130">이 이점은 다음 작업에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-130">This benefit is especially useful for the following tasks:</span></span>  
  
-   <span data-ttu-id="95d38-131">추적 및 진단 루틴 사용.</span><span class="sxs-lookup"><span data-stu-id="95d38-131">Using tracing and diagnostic routines.</span></span>  
  
-   <span data-ttu-id="95d38-132">데이터를 바인딩할 때 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스 구현.</span><span class="sxs-lookup"><span data-stu-id="95d38-132">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="95d38-133">이 인터페이스에서는 컨트롤에서 업데이트된 정보를 표시할 수 있도록 바운드 컨트롤의 속성이 변경되었음을 알리는 개체의 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-133">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="95d38-134">`CallerMemberName` 특성이 없으면 속성 이름을 리터럴로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-134">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>  
  
 <span data-ttu-id="95d38-135">아래 차트는 `CallerMemberName` 특성을 사용할 때 반환되는 멤버 이름을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-135">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>  
  
|<span data-ttu-id="95d38-136">호출 발생 범위</span><span class="sxs-lookup"><span data-stu-id="95d38-136">Calls occurs within</span></span>|<span data-ttu-id="95d38-137">멤버 이름 결과</span><span class="sxs-lookup"><span data-stu-id="95d38-137">Member name result</span></span>|  
|-------------------------|------------------------|  
|<span data-ttu-id="95d38-138">메서드, 속성 또는 이벤트</span><span class="sxs-lookup"><span data-stu-id="95d38-138">Method, property, or event</span></span>|<span data-ttu-id="95d38-139">호출에서 시작한 메서드, 속성 또는 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-139">The name of the method, property, or event from which the call originated.</span></span>|  
|<span data-ttu-id="95d38-140">생성자</span><span class="sxs-lookup"><span data-stu-id="95d38-140">Constructor</span></span>|<span data-ttu-id="95d38-141">".ctor" 문자열</span><span class="sxs-lookup"><span data-stu-id="95d38-141">The string ".ctor"</span></span>|  
|<span data-ttu-id="95d38-142">정적 생성자</span><span class="sxs-lookup"><span data-stu-id="95d38-142">Static constructor</span></span>|<span data-ttu-id="95d38-143">".cctor" 문자열</span><span class="sxs-lookup"><span data-stu-id="95d38-143">The string ".cctor"</span></span>|  
|<span data-ttu-id="95d38-144">소멸자</span><span class="sxs-lookup"><span data-stu-id="95d38-144">Destructor</span></span>|<span data-ttu-id="95d38-145">"Finalize" 문자열</span><span class="sxs-lookup"><span data-stu-id="95d38-145">The string "Finalize"</span></span>|  
|<span data-ttu-id="95d38-146">사용자 정의 연산자 또는 변환</span><span class="sxs-lookup"><span data-stu-id="95d38-146">User-defined operators or conversions</span></span>|<span data-ttu-id="95d38-147">멤버에 대해 생성되는 이름입니다(예: "op_Addition").</span><span class="sxs-lookup"><span data-stu-id="95d38-147">The generated name for the member, for example, "op_Addition".</span></span>|  
|<span data-ttu-id="95d38-148">특성 생성자</span><span class="sxs-lookup"><span data-stu-id="95d38-148">Attribute constructor</span></span>|<span data-ttu-id="95d38-149">특성이 적용되는 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-149">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="95d38-150">특성이 멤버 내에 있는 어떤 요소인 경우(예: 매개 변수, 반환 값 또는 제네릭 형식 매개 변수) 이 결과는 그 요소와 관련된 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-150">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|  
|<span data-ttu-id="95d38-151">포함하는 멤버가 없음(예: 어셈블리 수준 또는 형식에 적용되는 특성)</span><span class="sxs-lookup"><span data-stu-id="95d38-151">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="95d38-152">선택적 매개 변수의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="95d38-152">The default value of the optional parameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95d38-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95d38-153">See Also</span></span>  
 [<span data-ttu-id="95d38-154">특성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95d38-154">Attributes (Visual Basic)</span></span>](../../../visual-basic/language-reference/attributes.md)  
 [<span data-ttu-id="95d38-155">일반 특성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95d38-155">Common Attributes (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md)  
 [<span data-ttu-id="95d38-156">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="95d38-156">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [<span data-ttu-id="95d38-157">프로그래밍 개념(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95d38-157">Programming Concepts (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/index.md)
