---
title: "방법: Windows API 호출(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a219e031cdd36c713db8dcee6cc1da3849c9cf93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="5ee75-102">방법: Windows API 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ee75-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="5ee75-103">정의 하 고 호출 하는이 예제는 `MessageBox` user32.dll의 함수에는 문자열을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee75-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ee75-104">예제</span><span class="sxs-lookup"><span data-stu-id="5ee75-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5ee75-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5ee75-105">Compiling the Code</span></span>  
 <span data-ttu-id="5ee75-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee75-106">This example requires:</span></span>  
  
-   <span data-ttu-id="5ee75-107"><xref:System> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="5ee75-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="5ee75-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="5ee75-108">Robust Programming</span></span>  
 <span data-ttu-id="5ee75-109">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee75-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="5ee75-110">메서드가 정적이 아니거나,는 추상 클래스 또는 이전에 정의 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee75-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="5ee75-111">부모 형식이 인터페이스 또는 길이의 *이름* 또는 *dllName* 은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="5ee75-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="5ee75-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="5ee75-112">(<xref:System.ArgumentException>)</span></span>  
  
-   <span data-ttu-id="5ee75-113">*이름* 또는 *dllName* 은 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee75-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="5ee75-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="5ee75-114">(<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="5ee75-115">포함하는 형식은 `CreateType`을 사용하여 이전에 만든 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5ee75-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="5ee75-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="5ee75-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee75-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ee75-117">See Also</span></span>  
 [<span data-ttu-id="5ee75-118">좀 더 자세히 살펴보고 플랫폼 호출</span><span class="sxs-lookup"><span data-stu-id="5ee75-118">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [<span data-ttu-id="5ee75-119">플랫폼 호출 예제</span><span class="sxs-lookup"><span data-stu-id="5ee75-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="5ee75-120">관리되지 않는 DLL 함수 사용</span><span class="sxs-lookup"><span data-stu-id="5ee75-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
 [<span data-ttu-id="5ee75-121">내보내기를 리플렉션 사용 하 여 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee75-121">Defining a Method with Reflection Emit</span></span>](http://msdn.microsoft.com/en-us/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
 [<span data-ttu-id="5ee75-122">연습: Windows API 호출</span><span class="sxs-lookup"><span data-stu-id="5ee75-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [<span data-ttu-id="5ee75-123">COM Interop</span><span class="sxs-lookup"><span data-stu-id="5ee75-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
