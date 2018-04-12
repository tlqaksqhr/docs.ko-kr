---
title: Error 문
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3cd3245fd3e9e62b1b6443e9787c97808a0d179d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="error-statement"></a><span data-ttu-id="9d180-102">Error 문</span><span class="sxs-lookup"><span data-stu-id="9d180-102">Error Statement</span></span>
<span data-ttu-id="9d180-103">오류 발생을 시뮬레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="9d180-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d180-104">구문</span><span class="sxs-lookup"><span data-stu-id="9d180-104">Syntax</span></span>  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="9d180-105">요소</span><span class="sxs-lookup"><span data-stu-id="9d180-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="9d180-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="9d180-106">Required.</span></span> <span data-ttu-id="9d180-107">모든 유효한 오류 숫자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d180-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d180-108">설명</span><span class="sxs-lookup"><span data-stu-id="9d180-108">Remarks</span></span>  
 <span data-ttu-id="9d180-109">`Error` 문은 이전 버전과 호환성을 위해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d180-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="9d180-110">새 코드, 특히 개체를 만들 때 사용 하 여는 `Err` 개체의 `Raise` 런타임 오류를 생성 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="9d180-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="9d180-111">경우 `errornumber` 정의 된는 `Error` 문 뒤의 속성을 오류 처리기를 호출는 `Err` 개체에는 다음과 같은 기본값이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d180-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="9d180-112">속성</span><span class="sxs-lookup"><span data-stu-id="9d180-112">Property</span></span>|<span data-ttu-id="9d180-113">값</span><span class="sxs-lookup"><span data-stu-id="9d180-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="9d180-114">인수로 지정 된 값 `Error` 문.</span><span class="sxs-lookup"><span data-stu-id="9d180-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="9d180-115">모든 유효한 오류 숫자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d180-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="9d180-116">현재 Visual Basic 프로젝트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9d180-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="9d180-117">문자열 식의 반환 값에 해당 하는 `Error` 지정 된 함수 `Number`이 문자열이 있으면, 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d180-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="9d180-118">문자열이 없는 경우 `Description` 는 길이가 0 인 문자열을 포함 ("").</span><span class="sxs-lookup"><span data-stu-id="9d180-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="9d180-119">정규화 된 드라이브, 경로 및 적절 한 Visual Basic 도움말 파일의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9d180-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="9d180-120">적절 한 Visual Basic 도움말 파일 컨텍스트 ID에 해당 하는 오류에 대 한는 `Number` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9d180-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="9d180-121">0입니다.</span><span class="sxs-lookup"><span data-stu-id="9d180-121">Zero.</span></span>|  
  
 <span data-ttu-id="9d180-122">오류 처리기 존재 하지 않거나 오류 메시지가 생성 되어에서 표시 none을 사용 하는 경우는 `Err` 개체의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9d180-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d180-123">일부 Visual Basic 호스트 응용 프로그램 개체를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d180-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="9d180-124">클래스 및 개체를 만들 수 있는지 확인 하려면 호스트 응용 프로그램의 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9d180-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d180-125">예제</span><span class="sxs-lookup"><span data-stu-id="9d180-125">Example</span></span>  
 <span data-ttu-id="9d180-126">사용 하 여이 예제는 `Error` 문의 오류 번호 11을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d180-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="9d180-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9d180-127">Requirements</span></span>  
 <span data-ttu-id="9d180-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="9d180-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="9d180-129">**어셈블리:** Visual Basic 런타임 라이브러리 (Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="9d180-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d180-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d180-130">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>  
 [<span data-ttu-id="9d180-131">On Error 문</span><span class="sxs-lookup"><span data-stu-id="9d180-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)  
 [<span data-ttu-id="9d180-132">Resume 문</span><span class="sxs-lookup"><span data-stu-id="9d180-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [<span data-ttu-id="9d180-133">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="9d180-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
