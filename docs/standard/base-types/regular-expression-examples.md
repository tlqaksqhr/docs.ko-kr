---
title: "정규식 예제"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- regular expressions [.NET Framework], examples
- regular expressions [.NET Framework]
- strings [.NET Framework], regular expressions
ms.assetid: e9fd53f2-ed56-4b09-b2ea-e9bc9d65e6d6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d7fa8fe2bade9f20f71f846c717d79d6b6ffb36
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-examples"></a><span data-ttu-id="98c1b-102">정규식 예제</span><span class="sxs-lookup"><span data-stu-id="98c1b-102">Regular Expression Examples</span></span>
<span data-ttu-id="98c1b-103">이 섹션은 일반적인 응용 프로그램에서 정규식 사용을 보여 주는 코드 예제를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="98c1b-103">This section contains code examples that illustrate the use of regular expressions in common applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98c1b-104"><xref:System.Web.RegularExpressions> 네임 스페이스에는 HTML, XML 및 ASP.NET 문서에서 문자열 구문 분석 하기 위한 미리 정의 된 정규식 패턴을 구현 하는 정규식 개체 수가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c1b-104">The <xref:System.Web.RegularExpressions> namespace contains a number of regular expression objects that implement predefined regular expression patterns for parsing strings from HTML, XML, and ASP.NET documents.</span></span> <span data-ttu-id="98c1b-105">예를 들어는 <xref:System.Web.RegularExpressions.TagRegex> 문자열의 시작 태그를 식별 하는 클래스 및 <xref:System.Web.RegularExpressions.CommentRegex> 클래스는 문자열의 ASP.NET 주석을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c1b-105">For example, the <xref:System.Web.RegularExpressions.TagRegex> class identifies start tags in a string and the <xref:System.Web.RegularExpressions.CommentRegex> class identifies ASP.NET comments in a string.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98c1b-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="98c1b-106">In This Section</span></span>  
 [<span data-ttu-id="98c1b-107">예제: HREF 스캐닝</span><span class="sxs-lookup"><span data-stu-id="98c1b-107">Example: Scanning for HREFs</span></span>](../../../docs/standard/base-types/regular-expression-example-scanning-for-hrefs.md)  
 <span data-ttu-id="98c1b-108">입력된 문자열을 검색 하 고 모든 href 주는 예제를 제공 = "...".</span><span class="sxs-lookup"><span data-stu-id="98c1b-108">Provides an example that searches an input string and prints out all the href="…" values and their locations in the string.</span></span>  
  
 [<span data-ttu-id="98c1b-109">예제: 날짜 형식 변경</span><span class="sxs-lookup"><span data-stu-id="98c1b-109">Example: Changing Date Formats</span></span>](../../../docs/standard/base-types/regular-expression-example-changing-date-formats.md)  
 <span data-ttu-id="98c1b-110">폼 일-m m-년의 날짜는 양식 mm/dd/yy의 날짜를 대체 하는 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c1b-110">Provides an example that replaces dates in the form mm/dd/yy with dates in the form dd-mm-yy.</span></span>  
  
 [<span data-ttu-id="98c1b-111">방법: URL에서 프로토콜 및 포트 번호 추출</span><span class="sxs-lookup"><span data-stu-id="98c1b-111">How to: Extract a Protocol and Port Number from a URL</span></span>](../../../docs/standard/base-types/how-to-extract-a-protocol-and-port-number-from-a-url.md)  
 <span data-ttu-id="98c1b-112">URL이 포함 된 문자열에서 프로토콜 및 포트 번호를 추출 하는 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c1b-112">Provides an example that extracts a protocol and port number from a string that contains a URL.</span></span> <span data-ttu-id="98c1b-113">예를 들어 "http://www.contoso.com:8080/letters/readme.html"은 "http:8080"을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="98c1b-113">For example, "http://www.contoso.com:8080/letters/readme.html" returns "http:8080".</span></span>  
  
 [<span data-ttu-id="98c1b-114">방법: 문자열에서 유효하지 않은 문자 제거</span><span class="sxs-lookup"><span data-stu-id="98c1b-114">How to: Strip Invalid Characters from a String</span></span>](../../../docs/standard/base-types/how-to-strip-invalid-characters-from-a-string.md)  
 <span data-ttu-id="98c1b-115">문자열에서 잘못 된 영숫자가 아닌 문자를 제거 하는 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c1b-115">Provides an example that strips invalid non-alphanumeric characters from a string.</span></span>  
  
 [<span data-ttu-id="98c1b-116">방법: 문자열이 올바른 전자 메일 형식인지 확인</span><span class="sxs-lookup"><span data-stu-id="98c1b-116">How to: Verify that Strings Are in Valid Email Format</span></span>](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md)  
 <span data-ttu-id="98c1b-117">문자열이 유효한 전자 메일 형식인지 확인하는 데 사용할 수 있는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="98c1b-117">Provides an example that you can use to verify that a string is in valid email format.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="98c1b-118">참조</span><span class="sxs-lookup"><span data-stu-id="98c1b-118">Reference</span></span>  
 <xref:System.Text.RegularExpressions>  
 <span data-ttu-id="98c1b-119">.NET 클래스 라이브러리 참조 정보를 제공 **System.Text.RegularExpressions** 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="98c1b-119">Provides class library reference information for the .NET **System.Text.RegularExpressions** namespace.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="98c1b-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="98c1b-120">Related Sections</span></span>  
 [<span data-ttu-id="98c1b-121">.NET 정규식</span><span class="sxs-lookup"><span data-stu-id="98c1b-121">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)  
 <span data-ttu-id="98c1b-122">정규식의 프로그래밍 언어 측면에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="98c1b-122">Provides an overview of the programming language aspect of regular expressions.</span></span>  
  
 [<span data-ttu-id="98c1b-123">정규식 개체 모델</span><span class="sxs-lookup"><span data-stu-id="98c1b-123">The Regular Expression Object Model</span></span>](../../../docs/standard/base-types/the-regular-expression-object-model.md)  
 <span data-ttu-id="98c1b-124">정규식 클래스에 포함 된 설명는 `System.Text.RegularExpression` 네임 스페이스 고 목록과 해당 사용법은 예를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c1b-124">Describes the regular expression classes contained in the `System.Text.RegularExpression` namespace and provides examples of their use.</span></span>  
  
 [<span data-ttu-id="98c1b-125">정규식 동작 정보</span><span class="sxs-lookup"><span data-stu-id="98c1b-125">Details of Regular Expression Behavior</span></span>](../../../docs/standard/base-types/details-of-regular-expression-behavior.md)  
 <span data-ttu-id="98c1b-126">기능 및.NET 정규식의 동작에 대 한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="98c1b-126">Provides information about the capabilities and behavior of .NET regular expressions.</span></span>  
  
 [<span data-ttu-id="98c1b-127">정규식 언어 - 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="98c1b-127">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 <span data-ttu-id="98c1b-128">정규식을 정의하는 데 사용할 수 있는 문자, 연산자 및 생성자 집합에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="98c1b-128">Provides information on the set of characters, operators, and constructs that you can use to define regular expressions.</span></span>
