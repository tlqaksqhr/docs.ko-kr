---
title: ".NET Framework의 기본적인 문자열 작업"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strings [.NET Framework], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f241b99f97cad081a65fd8654169e444a1b588cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="a9c49-102">.NET의 기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="a9c49-102">Basic String Operations in .NET</span></span>
<span data-ttu-id="a9c49-103">응용 프로그램에서 사용자 입력을 기반으로 메시지를 생성하여 사용자에게 응답하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c49-103">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="a9c49-104">예를 들어 웹 사이트에서 사용자 이름을 포함하는 특수 인사말을 사용하여 새로 로그온한 사용자에게 응답하는 경우도 드물지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c49-104">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="a9c49-105">일부 메서드는 <xref:System.String?displayProperty=nameWithType> 및 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 클래스를 사용 하면을 동적으로 사용자 인터페이스에 표시할 사용자 지정 문자열을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c49-105">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="a9c49-106">이러한 메서드는 바이트 배열에서 새 문자열 만들기, 문자열 값 비교, 기존 문자열 수정 등의 여러 기본적인 문자열 작업을 수행하는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9c49-106">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a9c49-107">단원 내용</span><span class="sxs-lookup"><span data-stu-id="a9c49-107">In This Section</span></span>  
 [<span data-ttu-id="a9c49-108">새 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="a9c49-108">Creating New Strings</span></span>](../../../docs/standard/base-types/creating-new.md)  
 <span data-ttu-id="a9c49-109">개체를 문자열로 변환 하 고 문자열을 결합 하는 기본적인 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c49-109">Describes basic ways to convert objects into strings and to combine strings.</span></span>  
  
 [<span data-ttu-id="a9c49-110">문자 트리밍 및 제거</span><span class="sxs-lookup"><span data-stu-id="a9c49-110">Trimming and Removing Characters</span></span>](../../../docs/standard/base-types/trimming.md)  
 <span data-ttu-id="a9c49-111">Trim 또는 문자열의 문자를 제거 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c49-111">Describes how to trim or remove characters in a string.</span></span>  
  
 [<span data-ttu-id="a9c49-112">문자열 채우기</span><span class="sxs-lookup"><span data-stu-id="a9c49-112">Padding Strings</span></span>](../../../docs/standard/base-types/padding.md)  
 <span data-ttu-id="a9c49-113">문자열에 문자 또는 공백을 삽입하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c49-113">Describes how to insert characters or empty spaces into a string.</span></span>  
  
 [<span data-ttu-id="a9c49-114">문자열 비교</span><span class="sxs-lookup"><span data-stu-id="a9c49-114">Comparing Strings</span></span>](../../../docs/standard/base-types/comparing.md)  
 <span data-ttu-id="a9c49-115">두 개 이상의 문자열의 내용을 비교 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c49-115">Describes how to compare the contents of two or more strings.</span></span>  
  
 [<span data-ttu-id="a9c49-116">대/소문자 바꾸기</span><span class="sxs-lookup"><span data-stu-id="a9c49-116">Changing Case</span></span>](../../../docs/standard/base-types/changing-case.md)  
 <span data-ttu-id="a9c49-117">문자열 내 문자의 대/소문자를 변경 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c49-117">Describes how to change the case of characters within a string.</span></span>  
  
 [<span data-ttu-id="a9c49-118">StringBuilder 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="a9c49-118">Using the StringBuilder Class</span></span>](../../../docs/standard/base-types/stringbuilder.md)  
 <span data-ttu-id="a9c49-119">만들고 동적 문자열 개체를 수정 하는 방법에 설명 된 <xref:System.Text.StringBuilder> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a9c49-119">Describes how to create and modify dynamic string objects with the <xref:System.Text.StringBuilder> class.</span></span>  
  
 [<span data-ttu-id="a9c49-120">방법: 기본적인 문자열 조작 수행</span><span class="sxs-lookup"><span data-stu-id="a9c49-120">How to: Perform Basic String Manipulations</span></span>](../../../docs/standard/base-types/basic-manipulations.md)  
 <span data-ttu-id="a9c49-121">기본적인 문자열 작업의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9c49-121">Demonstrates the use of basic string operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a9c49-122">관련 단원</span><span class="sxs-lookup"><span data-stu-id="a9c49-122">Related Sections</span></span>  
 [<span data-ttu-id="a9c49-123">.NET에서 형식 변환</span><span class="sxs-lookup"><span data-stu-id="a9c49-123">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="a9c49-124">형식을 다른 형식으로 변환 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c49-124">Describes how to convert one type into another type.</span></span>  
  
 [<span data-ttu-id="a9c49-125">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="a9c49-125">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="a9c49-126">형식 지정자를 사용 하 여 문자열의 서식을 지정 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c49-126">Describes how to format strings using format specifiers.</span></span>
