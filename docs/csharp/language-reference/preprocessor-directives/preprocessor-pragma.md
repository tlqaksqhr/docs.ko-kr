---
title: "#<a name=\"pragma-c-reference\"></a>pragma(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#pragma'
helpviewer_keywords: '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6f53bd0ed3f35f049b0a1cbb21c5b9a563f9fce9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="pragma-c-reference"></a><span data-ttu-id="36c12-102">#pragma(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="36c12-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="36c12-103">`#pragma`는 이 코드가 표시되는 파일의 컴파일에 대한 특수 명령을 컴파일러에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="36c12-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="36c12-104">컴파일러에서 명령을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c12-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="36c12-105">즉, `#pragma`를 사용하여 사용자 지정 전처리 명령을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36c12-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="36c12-106">Microsoft C# 컴파일러는 다음 두 가지 `#pragma` 명령을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="36c12-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="36c12-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="36c12-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="36c12-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="36c12-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="36c12-109">구문</span><span class="sxs-lookup"><span data-stu-id="36c12-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36c12-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="36c12-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="36c12-111">인식된 pragma의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="36c12-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="36c12-112">pragma 관련 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="36c12-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36c12-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36c12-113">See Also</span></span>  
 [<span data-ttu-id="36c12-114">C# 참조</span><span class="sxs-lookup"><span data-stu-id="36c12-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="36c12-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="36c12-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="36c12-116">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="36c12-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
 [<span data-ttu-id="36c12-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="36c12-117">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
 [<span data-ttu-id="36c12-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="36c12-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)
