---
title: "호출자 정보 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: 15d556eb-4d0c-4497-98a3-7f60abb7d6a1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d9a028474a3bb7ae020f466d4dfe51608c43ab07
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="caller-information-visual-basic"></a><span data-ttu-id="e1ebf-102">호출자 정보 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1ebf-102">Caller Information (Visual Basic)</span></span>
<span data-ttu-id="e1ebf-103">호출자 정보 특성을 사용하여 메서드 호출자에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-103">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="e1ebf-104">소스 코드 파일 경로, 소스 코드 줄 번호 및 호출자의 멤버 이름을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-104">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="e1ebf-105">이 정보는 추적, 디버깅 및 진단 도구를 만드는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-105">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>  
  
 <span data-ttu-id="e1ebf-106">이 정보를 얻으려면 각각 기본값이 있는 선택적 매개 변수에 적용되는 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-106">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="e1ebf-107">에 정의 된 호출자 정보 특성을 나열 하는 다음 표에 <xref:System.Runtime.CompilerServices?displayProperty=fullName>네임 스페이스:</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e1ebf-107">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace:</span></span>  
  
|<span data-ttu-id="e1ebf-108">특성</span><span class="sxs-lookup"><span data-stu-id="e1ebf-108">Attribute</span></span>|<span data-ttu-id="e1ebf-109">설명</span><span class="sxs-lookup"><span data-stu-id="e1ebf-109">Description</span></span>|<span data-ttu-id="e1ebf-110">형식</span><span class="sxs-lookup"><span data-stu-id="e1ebf-110">Type</span></span>|  
|---|---|---|  
|<span data-ttu-id="e1ebf-111"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span><span class="sxs-lookup"><span data-stu-id="e1ebf-111"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span></span>|<span data-ttu-id="e1ebf-112">호출자를 포함한 소스 파일의 전체 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-112">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="e1ebf-113">컴파일 시간의 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-113">This is the file path at compile time.</span></span>|`String`|  
|<span data-ttu-id="e1ebf-114"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span><span class="sxs-lookup"><span data-stu-id="e1ebf-114"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span></span>|<span data-ttu-id="e1ebf-115">메서드가 호출되는 소스 파일의 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-115">Line number in the source file at which the method is called.</span></span>|`Integer`|  
|<span data-ttu-id="e1ebf-116"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span><span class="sxs-lookup"><span data-stu-id="e1ebf-116"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span></span>|<span data-ttu-id="e1ebf-117">호출자의 메서드 또는 속성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-117">Method or property name of the caller.</span></span> <span data-ttu-id="e1ebf-118">참조 [멤버 이름](#MEMBERNAMES) 이 항목의 뒷부분에 나오는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-118">See [Member Names](#MEMBERNAMES) later in this topic.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="e1ebf-119">예제</span><span class="sxs-lookup"><span data-stu-id="e1ebf-119">Example</span></span>  
 <span data-ttu-id="e1ebf-120">다음 예제에서는 호출자 정보 특성을 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-120">The following example shows how to use Caller Info attributes.</span></span> <span data-ttu-id="e1ebf-121">`TraceMessage` 메서드에 대한 각 호출에서 호출자 정보는 선택적 매개 변수에 대한 인수로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-121">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="e1ebf-122">주의</span><span class="sxs-lookup"><span data-stu-id="e1ebf-122">Remarks</span></span>  
 <span data-ttu-id="e1ebf-123">각각의 선택적 매개 변수에 대한 명시적 기본값을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-123">You must specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="e1ebf-124">선택적으로 지정되지 않은 매개 변수에 호출자 정보 특성을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-124">You can't apply Caller Info attributes to parameters that aren't specified as optional.</span></span>  
  
 <span data-ttu-id="e1ebf-125">호출자 정보 특성은 매개 변수를 선택적 매개 변수로 만들지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-125">The Caller Info attributes don't make a parameter optional.</span></span> <span data-ttu-id="e1ebf-126">대신, 이런 특성은 인수가 생략될 때 전달되는 기본값에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-126">Instead, they affect the default value that's passed in when the argument is omitted.</span></span>  
  
 <span data-ttu-id="e1ebf-127">호출자 정보 값은 컴파일 시간에 리터럴로 중간 언어(IL) 내로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-127">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="e1ebf-128">결과 달리는 <xref:System.Exception.StackTrace%2A>예외를 결과 대 한 속성은 난독 화의 영향을 받지 않습니다.</xref:System.Exception.StackTrace%2A></span><span class="sxs-lookup"><span data-stu-id="e1ebf-128">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span>  
  
 <span data-ttu-id="e1ebf-129">선택적 인수를 명시적으로 제공하여 호출자 정보를 제어하거나 호출자 정보를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-129">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>  
  
###  <span data-ttu-id="e1ebf-130"><a name="MEMBERNAMES"></a>멤버 이름</span><span class="sxs-lookup"><span data-stu-id="e1ebf-130"><a name="MEMBERNAMES"></a> Member Names</span></span>  
 <span data-ttu-id="e1ebf-131">`CallerMemberName` 특성을 사용하여 멤버 이름을 호출된 메서드에 대한 `String` 인수로 지정하는 것을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-131">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="e1ebf-132">이 기법을 사용 하 여 문제를 방지 하는 **이름 바꾸기 리팩터링** 변경 되지 않습니다는 `String` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-132">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="e1ebf-133">이 이점은 다음 작업에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-133">This benefit is especially useful for the following tasks:</span></span>  
  
-   <span data-ttu-id="e1ebf-134">추적 및 진단 루틴 사용.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-134">Using tracing and diagnostic routines.</span></span>  
  
-   <span data-ttu-id="e1ebf-135">구현 된 <xref:System.ComponentModel.INotifyPropertyChanged>데이터 바인딩 인터페이스.</xref:System.ComponentModel.INotifyPropertyChanged></span><span class="sxs-lookup"><span data-stu-id="e1ebf-135">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="e1ebf-136">이 인터페이스에서는 컨트롤에서 업데이트된 정보를 표시할 수 있도록 바운드 컨트롤의 속성이 변경되었음을 알리는 개체의 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-136">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="e1ebf-137">`CallerMemberName` 특성이 없으면 속성 이름을 리터럴로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-137">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>  
  
 <span data-ttu-id="e1ebf-138">아래 차트는 `CallerMemberName` 특성을 사용할 때 반환되는 멤버 이름을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-138">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>  
  
|<span data-ttu-id="e1ebf-139">호출 발생 범위</span><span class="sxs-lookup"><span data-stu-id="e1ebf-139">Calls occurs within</span></span>|<span data-ttu-id="e1ebf-140">멤버 이름 결과</span><span class="sxs-lookup"><span data-stu-id="e1ebf-140">Member name result</span></span>|  
|-------------------------|------------------------|  
|<span data-ttu-id="e1ebf-141">메서드, 속성 또는 이벤트</span><span class="sxs-lookup"><span data-stu-id="e1ebf-141">Method, property, or event</span></span>|<span data-ttu-id="e1ebf-142">호출에서 시작한 메서드, 속성 또는 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-142">The name of the method, property, or event from which the call originated.</span></span>|  
|<span data-ttu-id="e1ebf-143">생성자</span><span class="sxs-lookup"><span data-stu-id="e1ebf-143">Constructor</span></span>|<span data-ttu-id="e1ebf-144">".ctor" 문자열</span><span class="sxs-lookup"><span data-stu-id="e1ebf-144">The string ".ctor"</span></span>|  
|<span data-ttu-id="e1ebf-145">정적 생성자</span><span class="sxs-lookup"><span data-stu-id="e1ebf-145">Static constructor</span></span>|<span data-ttu-id="e1ebf-146">".cctor" 문자열</span><span class="sxs-lookup"><span data-stu-id="e1ebf-146">The string ".cctor"</span></span>|  
|<span data-ttu-id="e1ebf-147">소멸자</span><span class="sxs-lookup"><span data-stu-id="e1ebf-147">Destructor</span></span>|<span data-ttu-id="e1ebf-148">"Finalize" 문자열</span><span class="sxs-lookup"><span data-stu-id="e1ebf-148">The string "Finalize"</span></span>|  
|<span data-ttu-id="e1ebf-149">사용자 정의 연산자 또는 변환</span><span class="sxs-lookup"><span data-stu-id="e1ebf-149">User-defined operators or conversions</span></span>|<span data-ttu-id="e1ebf-150">멤버에 대해 생성되는 이름입니다(예: "op_Addition").</span><span class="sxs-lookup"><span data-stu-id="e1ebf-150">The generated name for the member, for example, "op_Addition".</span></span>|  
|<span data-ttu-id="e1ebf-151">특성 생성자</span><span class="sxs-lookup"><span data-stu-id="e1ebf-151">Attribute constructor</span></span>|<span data-ttu-id="e1ebf-152">특성이 적용되는 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-152">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="e1ebf-153">특성이 멤버 내에 있는 어떤 요소인 경우(예: 매개 변수, 반환 값 또는 제네릭 형식 매개 변수) 이 결과는 그 요소와 관련된 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-153">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|  
|<span data-ttu-id="e1ebf-154">포함하는 멤버가 없음(예: 어셈블리 수준 또는 형식에 적용되는 특성)</span><span class="sxs-lookup"><span data-stu-id="e1ebf-154">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="e1ebf-155">선택적 매개 변수의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="e1ebf-155">The default value of the optional parameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1ebf-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1ebf-156">See Also</span></span>  
 <span data-ttu-id="e1ebf-157">[특성 (Visual Basic)](../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="e1ebf-157">[Attributes (Visual Basic)](../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="e1ebf-158"> [공통 특성 (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="e1ebf-158"> [Common Attributes (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) </span></span>  
<span data-ttu-id="e1ebf-159"> [선택적 매개 변수](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="e1ebf-159"> [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md) </span></span>  
<span data-ttu-id="e1ebf-160"> [프로그래밍 개념 (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="e1ebf-160"> [Programming Concepts (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)</span></span>
