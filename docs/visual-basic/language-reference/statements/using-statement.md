---
title: Using 문(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
caps.latest.revision: 36
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ed9cc0d04c89eac1fe342a0924dd89bb1e258a11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="64f12-102">Using 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64f12-102">Using Statement (Visual Basic)</span></span>
<span data-ttu-id="64f12-103">시작을 선언는 `Using` 차단 하 고 블록이 제어 되는 시스템 리소스를 선택적으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64f12-104">구문</span><span class="sxs-lookup"><span data-stu-id="64f12-104">Syntax</span></span>  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a><span data-ttu-id="64f12-105">요소</span><span class="sxs-lookup"><span data-stu-id="64f12-105">Parts</span></span>  
  
|<span data-ttu-id="64f12-106">용어</span><span class="sxs-lookup"><span data-stu-id="64f12-106">Term</span></span>|<span data-ttu-id="64f12-107">정의</span><span class="sxs-lookup"><span data-stu-id="64f12-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="64f12-108">지정 하지 않은 경우 필요한 `resourceexpression`합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="64f12-109">하나 이상의 시스템 리소스가이 목록 `Using` 쉼표로 구분 하 여 컨트롤을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="64f12-110">지정 하지 않은 경우 필요한 `resourcelist`합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="64f12-111">참조 변수 또는 시스템 리소스에 대 한이 제어를 참조 하는 식을 `Using` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="64f12-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-112">Optional.</span></span> <span data-ttu-id="64f12-113">문 블록을 하는 `Using` 블록이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="64f12-114">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="64f12-114">Required.</span></span> <span data-ttu-id="64f12-115">정의 종료는 `Using` 블록 및 제어 하는 모든 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  
  
 <span data-ttu-id="64f12-116">각 리소스에는 `resourcelist` 부분은 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 <span data-ttu-id="64f12-117">또는</span><span class="sxs-lookup"><span data-stu-id="64f12-117">-or-</span></span>  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a><span data-ttu-id="64f12-118">resourcelist 부분</span><span class="sxs-lookup"><span data-stu-id="64f12-118">resourcelist Parts</span></span>  
  
|<span data-ttu-id="64f12-119">용어</span><span class="sxs-lookup"><span data-stu-id="64f12-119">Term</span></span>|<span data-ttu-id="64f12-120">정의</span><span class="sxs-lookup"><span data-stu-id="64f12-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="64f12-121">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="64f12-121">Required.</span></span> <span data-ttu-id="64f12-122">참조 변수를 시스템 리소스를 참조 하는 `Using` 컨트롤을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="64f12-123">필요한 경우에는 `Using` 문이 리소스를 가져오는 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="64f12-124">이미 리소스를 확보 하는 경우에 두 번째 대체 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="64f12-125">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="64f12-125">Required.</span></span> <span data-ttu-id="64f12-126">리소스의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-126">The class of the resource.</span></span> <span data-ttu-id="64f12-127">클래스를 구현 해야 합니다는 <xref:System.IDisposable> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="64f12-128">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-128">Optional.</span></span> <span data-ttu-id="64f12-129">인스턴스를 만드는 생성자에 전달 하는 인수 목록 `resourcetype`합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="64f12-130">참조 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-130">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="64f12-131">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="64f12-131">Required.</span></span> <span data-ttu-id="64f12-132">변수 또는 식의 요구 사항을 만족 하는 시스템 리소스를 가리키는 `resourcetype`합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="64f12-133">컨트롤을 전달 하기 전에 리소스를 획득 해야 두 번째 대체 구문을 사용 하는 경우는 `Using` 문.</span><span class="sxs-lookup"><span data-stu-id="64f12-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64f12-134">설명</span><span class="sxs-lookup"><span data-stu-id="64f12-134">Remarks</span></span>  
 <span data-ttu-id="64f12-135">경우에 따라 코드는 열려 있는 파일 핸들, COM 래퍼 SQL 연결 등의 관리 되지 않는 리소스를 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="64f12-136">A `Using` 블록 코드는 작업을 마칠 때 하나 이상의 이러한 리소스의 삭제를 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="64f12-137">이 사용할 수 있도록 사용 하기 위해 다른 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-137">This makes them available for other code to use.</span></span>  
  
 <span data-ttu-id="64f12-138">관리 되는 리소스를 사용자의 추가 코딩 없이.NET Framework 가비지 수집기 (GC)에서 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="64f12-139">불필요 한 `Using` 관리 되는 리소스에 대 한 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="64f12-140">그러나 계속 사용할 수 있습니다는 `Using` 블록을 가비지 수집기에 대 한 대기 하지 않고 관리 되는 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="64f12-141">A `Using` 블록에는 세 부분으로 구성: 취득, 사용 및 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>  
  
-   <span data-ttu-id="64f12-142">*취득* 변수를 만들고 시스템 리소스를 참조 하 여 초기화 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="64f12-143">`Using` 문은 하나 이상의 리소스를 획득할 수 또는 블록에 들어가기 전에 정확히 한 개의 리소스를 획득 하 고에 제공할 수 있습니다는 `Using` 문.</span><span class="sxs-lookup"><span data-stu-id="64f12-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="64f12-144">제공 하는 경우 `resourceexpression`, 제어를 전달 하기 전에 해당 리소스를 취득 해야 합니다는 `Using` 문.</span><span class="sxs-lookup"><span data-stu-id="64f12-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>  
  
-   <span data-ttu-id="64f12-145">*사용 현황* 리소스에 액세스 하 고 사용 하 여 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="64f12-146">사이 있는 문은 `Using` 및 `End Using` 리소스 사용을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>  
  
-   <span data-ttu-id="64f12-147">*폐기* 호출 의미는 <xref:System.IDisposable.Dispose%2A> 개체에서 메서드 `resourcename`합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="64f12-148">따라서 개체를를 해당 리소스를 완전히 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="64f12-149">`End Using` 문 아래에 있는 리소스를 삭제는 `Using` 블록의 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="64f12-150">동작</span><span class="sxs-lookup"><span data-stu-id="64f12-150">Behavior</span></span>  
 <span data-ttu-id="64f12-151">A `Using` 블록 처럼 작동 한 `Try`... `Finally` 구문은 `Try` 리소스를 사용 하는 블록 및 `Finally` 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="64f12-152">이 인해는 `Using` 블록은 블록을 종료 하는 방법에 관계 없이 리소스의 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="64f12-153">이 경우에 처리 되지 않은 예외를 제외 하 고는 <xref:System.StackOverflowException>합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>  
  
 <span data-ttu-id="64f12-154">에 의해 획득 되는 모든 리소스 변수의 범위는 `Using` 문을로 제한 됩니다.는 `Using` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>  
  
 <span data-ttu-id="64f12-155">하나 이상의 시스템 리소스를 지정 하는 경우는 `Using` 중첩 문, 효과 동일 `Using` 내에 다른 하나를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>  
  
 <span data-ttu-id="64f12-156">경우 `resourcename` 은 `Nothing`에 대 한 호출이 <xref:System.IDisposable.Dispose%2A> 설정 되 면 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>  
  
## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="64f12-157">구조적된 예외 처리를 사용 하 여 블록 내에서</span><span class="sxs-lookup"><span data-stu-id="64f12-157">Structured Exception Handling Within a Using Block</span></span>  
 <span data-ttu-id="64f12-158">내에서 발생할 수 있는 예외를 처리 해야 하는 경우는 `Using` 블록 전체를 추가할 수 있습니다 `Try`... `Finally` 를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="64f12-159">한 경우를 처리 하는 경우 여기서는 `Using` 문을 아닙니다. 리소스를 획득 하기 위한 성공 여부를 테스트할 수 `resourcename` 은 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="64f12-160">Using 블록 대신 구조적된 예외 처리</span><span class="sxs-lookup"><span data-stu-id="64f12-160">Structured Exception Handling Instead of a Using Block</span></span>  
 <span data-ttu-id="64f12-161">보다 세부적인 제어를 사용 하는 리소스를 확보 하거나 추가 코드가 필요는 `Finally` 블록, 다시 작성할 수 있습니다는 `Using` 차단는 `Try`... `Finally` 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="64f12-162">다음 예제에서는 스 켈 레 톤 `Try` 및 `Using` 가져오기 및 삭제에 해당 하는 구문을 `resource`합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>  
  
```vb  
Using resource As New resourceType   
    ' Insert code to work with resource.  
End Using  
  
' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.  
Dim resource As New resourceType  
Try   
    ' Insert code to work with resource.  
Finally   
    If resource IsNot Nothing Then  
        resource.Dispose()   
    End If  
End Try   
```  
  
> [!NOTE]
>  <span data-ttu-id="64f12-163">내의 코드는 `Using` 블록에 있는 개체를 할당 안 `resourcename` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="64f12-164">종료 하면는 `Using` 블록, 리소스가 삭제 되 고 다른 변수 가리키는 리소스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64f12-165">예제</span><span class="sxs-lookup"><span data-stu-id="64f12-165">Example</span></span>  
 <span data-ttu-id="64f12-166">다음 예제에서는 log.txt의 이름이 고 두 줄 텍스트 파일에 기록 하는 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="64f12-167">이 예제에서는 또한 파일 읽고 줄의 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-167">The example also reads that same file and displays the lines of text.</span></span>  
  
 <span data-ttu-id="64f12-168">때문에 <xref:System.IO.TextWriter> 및 <xref:System.IO.TextReader> 클래스 구현에서 <xref:System.IDisposable> 는 코드에서 사용할 수 있는 인터페이스를 `Using` 문을 파일 올바르게 닫힌 쓰기 및 읽기 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="64f12-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>  
  
 [!code-vb[VbVbalrStatements#50](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/using-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="64f12-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64f12-169">See Also</span></span>  
 <xref:System.IDisposable>  
 [<span data-ttu-id="64f12-170">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="64f12-170">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="64f12-171">방법: 시스템 리소스 해제</span><span class="sxs-lookup"><span data-stu-id="64f12-171">How to: Dispose of a System Resource</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
