---
title: '방법: Windows API 호출(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: de568c3273d4d040c6566136e5d59e2155b86f8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643642"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="6e3e6-102">방법: Windows API 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e3e6-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="6e3e6-103">정의 하 고 호출 하는이 예제는 `MessageBox` user32.dll의 함수에는 문자열을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3e6-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e3e6-104">예제</span><span class="sxs-lookup"><span data-stu-id="6e3e6-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6e3e6-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="6e3e6-105">Compiling the Code</span></span>  
 <span data-ttu-id="6e3e6-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3e6-106">This example requires:</span></span>  
  
-   <span data-ttu-id="6e3e6-107"><xref:System> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="6e3e6-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6e3e6-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="6e3e6-108">Robust Programming</span></span>  
 <span data-ttu-id="6e3e6-109">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3e6-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="6e3e6-110">메서드가 정적이 아니거나,는 추상 클래스 또는 이전에 정의 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3e6-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="6e3e6-111">부모 형식이 인터페이스 또는 길이의 *이름* 또는 *dllName* 은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="6e3e6-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="6e3e6-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="6e3e6-112">(<xref:System.ArgumentException>)</span></span>  
  
-   <span data-ttu-id="6e3e6-113">*이름* 또는 *dllName* 은 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3e6-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="6e3e6-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="6e3e6-114">(<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="6e3e6-115">포함하는 형식은 `CreateType`을 사용하여 이전에 만든 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6e3e6-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="6e3e6-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="6e3e6-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e3e6-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e3e6-117">See Also</span></span>  
 [<span data-ttu-id="6e3e6-118">플랫폼 호출 자세히 보기</span><span class="sxs-lookup"><span data-stu-id="6e3e6-118">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [<span data-ttu-id="6e3e6-119">플랫폼 호출 예제</span><span class="sxs-lookup"><span data-stu-id="6e3e6-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="6e3e6-120">관리되지 않는 DLL 함수 사용</span><span class="sxs-lookup"><span data-stu-id="6e3e6-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
 [<span data-ttu-id="6e3e6-121">내보내기를 리플렉션 사용 하 여 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3e6-121">Defining a Method with Reflection Emit</span></span>](http://msdn.microsoft.com/library/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
 [<span data-ttu-id="6e3e6-122">연습: Windows API 호출</span><span class="sxs-lookup"><span data-stu-id="6e3e6-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [<span data-ttu-id="6e3e6-123">COM Interop</span><span class="sxs-lookup"><span data-stu-id="6e3e6-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
