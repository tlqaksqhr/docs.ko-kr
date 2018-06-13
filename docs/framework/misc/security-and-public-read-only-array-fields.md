---
title: 보안 및 공용 읽기 전용 배열 필드
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0110bb42775d8a5df9ca268b35db3abaffec84f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33392631"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="ac75d-102">보안 및 공용 읽기 전용 배열 필드</span><span class="sxs-lookup"><span data-stu-id="ac75d-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="ac75d-103">읽기 전용 공용 배열 필드를 수정할 수 있기 때문에 경계 동작이 나 응용 프로그램의 보안을 정의 하는 관리 되는 라이브러리에서 읽기 전용 공용 배열 필드를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ac75d-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac75d-104">설명</span><span class="sxs-lookup"><span data-stu-id="ac75d-104">Remarks</span></span>  
 <span data-ttu-id="ac75d-105">일부.NET framework 클래스에는 플랫폼 특정 경계 매개 변수가 포함 된 읽기 전용 공용 필드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac75d-105">Some .NET framework classes include read-only public fields that contain platform-specific boundary parameters.</span></span>  <span data-ttu-id="ac75d-106">예를 들어는 <xref:System.IO.Path.InvalidPathChars> 필드는 파일 경로 문자열에서 허용 되지 않는 문자를 설명 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ac75d-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span>  <span data-ttu-id="ac75d-107">.NET Framework 전반에 걸쳐 많은 것과 유사한 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac75d-107">Many similar fields are present throughout the .NET Framework.</span></span>  
  
 <span data-ttu-id="ac75d-108">와 같은 공용 읽기 전용 필드의 값 <xref:System.IO.Path.InvalidPathChars> 코드 또는 사용자 코드의 응용 프로그램 도메인을 공유 하 여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac75d-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="ac75d-109">응용 프로그램의 경계 동작을 정의 하려면 다음과 같이 읽기 전용 공용 배열 필드를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ac75d-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="ac75d-110">이렇게 하면 악의적인 코드는 경계 정의 변경 하 고 코드를 사용 하 여 예기치 않은 방법으로 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac75d-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="ac75d-111">2.0 및.NET Framework의 나중 버전에서 공용 배열 필드를 사용 하는 대신 새 배열을 반환 하는 메서드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac75d-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="ac75d-112">예를 들어, 사용 하는 대신는 <xref:System.IO.Path.InvalidPathChars> 필드를 사용할지는 <xref:System.IO.Path.GetInvalidPathChars%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="ac75d-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="ac75d-113">참고가.NET Framework 형식 경계 유형을 내부적으로 정의 하는 공용 필드를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ac75d-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="ac75d-114">대신,.NET Framework는 별도 전용 필드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac75d-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="ac75d-115">이러한 공용 필드의 값을 변경 하는 경우에.NET Framework 형식의 동작을 변경 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac75d-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac75d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac75d-116">See Also</span></span>  
 [<span data-ttu-id="ac75d-117">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="ac75d-117">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
