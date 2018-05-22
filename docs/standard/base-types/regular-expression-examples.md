---
title: 정규식 예제
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- regular expressions [.NET Framework], examples
- regular expressions [.NET Framework]
- strings [.NET Framework], regular expressions
ms.assetid: e9fd53f2-ed56-4b09-b2ea-e9bc9d65e6d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fb58f8e7a1fef711de28534fbe53dfc9d7084ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="regular-expression-examples"></a><span data-ttu-id="7574d-102">정규식 예제</span><span class="sxs-lookup"><span data-stu-id="7574d-102">Regular Expression Examples</span></span>
<span data-ttu-id="7574d-103">이 섹션은 일반적인 응용 프로그램에서 정규식 사용을 보여 주는 코드 예제를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7574d-103">This section contains code examples that illustrate the use of regular expressions in common applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7574d-104"><xref:System.Web.RegularExpressions> 네임스페이스에는 HTML, XML 및 ASP.NET 문서의 문자열을 구문 분석하기 위해 미리 정의된 정규식 패턴을 구현하는 여러 정규식 개체가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7574d-104">The <xref:System.Web.RegularExpressions> namespace contains a number of regular expression objects that implement predefined regular expression patterns for parsing strings from HTML, XML, and ASP.NET documents.</span></span> <span data-ttu-id="7574d-105">예를 들어 <xref:System.Web.RegularExpressions.TagRegex> 클래스는 문자열의 시작 태그를 식별하고, <xref:System.Web.RegularExpressions.CommentRegex> 클래스는 문자열의 ASP.NET 주석을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="7574d-105">For example, the <xref:System.Web.RegularExpressions.TagRegex> class identifies start tags in a string and the <xref:System.Web.RegularExpressions.CommentRegex> class identifies ASP.NET comments in a string.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7574d-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="7574d-106">In This Section</span></span>  
 [<span data-ttu-id="7574d-107">예제: HREF 스캐닝</span><span class="sxs-lookup"><span data-stu-id="7574d-107">Example: Scanning for HREFs</span></span>](../../../docs/standard/base-types/regular-expression-example-scanning-for-hrefs.md)  
 <span data-ttu-id="7574d-108">입력 문자열을 검색하고 모든 href=“…” 값과 문자열에서의 해당 위치를 출력하는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7574d-108">Provides an example that searches an input string and prints out all the href="…" values and their locations in the string.</span></span>  
  
 [<span data-ttu-id="7574d-109">예제: 날짜 형식 변경</span><span class="sxs-lookup"><span data-stu-id="7574d-109">Example: Changing Date Formats</span></span>](../../../docs/standard/base-types/regular-expression-example-changing-date-formats.md)  
 <span data-ttu-id="7574d-110">mm/dd/yy 서식의 날짜를 dd-mm-yy 서식의 날짜로 바꾸는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7574d-110">Provides an example that replaces dates in the form mm/dd/yy with dates in the form dd-mm-yy.</span></span>  
  
 [<span data-ttu-id="7574d-111">방법: URL에서 프로토콜 및 포트 번호 추출</span><span class="sxs-lookup"><span data-stu-id="7574d-111">How to: Extract a Protocol and Port Number from a URL</span></span>](../../../docs/standard/base-types/how-to-extract-a-protocol-and-port-number-from-a-url.md)  
 <span data-ttu-id="7574d-112">URL이 포함된 문자열에서 프로토콜 및 포트 번호를 추출하는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7574d-112">Provides an example that extracts a protocol and port number from a string that contains a URL.</span></span> <span data-ttu-id="7574d-113">예를 들어 "http://www.contoso.com:8080/letters/readme.html"은 "http:8080"을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7574d-113">For example, "http://www.contoso.com:8080/letters/readme.html" returns "http:8080".</span></span>  
  
 [<span data-ttu-id="7574d-114">방법: 문자열에서 유효하지 않은 문자 제거</span><span class="sxs-lookup"><span data-stu-id="7574d-114">How to: Strip Invalid Characters from a String</span></span>](../../../docs/standard/base-types/how-to-strip-invalid-characters-from-a-string.md)  
 <span data-ttu-id="7574d-115">문자열에서 유효하지 않은 영숫자가 아닌 문자를 제거하는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7574d-115">Provides an example that strips invalid non-alphanumeric characters from a string.</span></span>  
  
 [<span data-ttu-id="7574d-116">방법: 문자열이 올바른 전자 메일 형식인지 확인</span><span class="sxs-lookup"><span data-stu-id="7574d-116">How to: Verify that Strings Are in Valid Email Format</span></span>](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md)  
 <span data-ttu-id="7574d-117">문자열이 유효한 전자 메일 형식인지 확인하는 데 사용할 수 있는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7574d-117">Provides an example that you can use to verify that a string is in valid email format.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7574d-118">참조</span><span class="sxs-lookup"><span data-stu-id="7574d-118">Reference</span></span>  
 <xref:System.Text.RegularExpressions>  
 <span data-ttu-id="7574d-119">.NET **System.Text.RegularExpressions** 네임스페이스에 대한 클래스 라이브러리 참조 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7574d-119">Provides class library reference information for the .NET **System.Text.RegularExpressions** namespace.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7574d-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="7574d-120">Related Sections</span></span>  
 [<span data-ttu-id="7574d-121">.NET 정규식</span><span class="sxs-lookup"><span data-stu-id="7574d-121">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)  
 <span data-ttu-id="7574d-122">정규식의 프로그래밍 언어 측면에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7574d-122">Provides an overview of the programming language aspect of regular expressions.</span></span>  
  
 [<span data-ttu-id="7574d-123">정규식 개체 모델</span><span class="sxs-lookup"><span data-stu-id="7574d-123">The Regular Expression Object Model</span></span>](../../../docs/standard/base-types/the-regular-expression-object-model.md)  
 <span data-ttu-id="7574d-124">`System.Text.RegularExpression` 네임스페이스에 포함된 정규식 클래스를 설명하고 이를 사용하는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7574d-124">Describes the regular expression classes contained in the `System.Text.RegularExpression` namespace and provides examples of their use.</span></span>  
  
 [<span data-ttu-id="7574d-125">정규식 동작 정보</span><span class="sxs-lookup"><span data-stu-id="7574d-125">Details of Regular Expression Behavior</span></span>](../../../docs/standard/base-types/details-of-regular-expression-behavior.md)  
 <span data-ttu-id="7574d-126">.NET 정규식의 기능 및 동작에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7574d-126">Provides information about the capabilities and behavior of .NET regular expressions.</span></span>  
  
 [<span data-ttu-id="7574d-127">정규식 언어 - 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="7574d-127">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 <span data-ttu-id="7574d-128">정규식을 정의하는 데 사용할 수 있는 문자, 연산자 및 생성자 집합에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7574d-128">Provides information on the set of characters, operators, and constructs that you can use to define regular expressions.</span></span>
