---
title: "대/소문자 표기법"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1bddb7bb3559e6f39b7884b92f64bee8fbb3510
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="capitalization-conventions"></a><span data-ttu-id="14dd8-102">대/소문자 표기법</span><span class="sxs-lookup"><span data-stu-id="14dd8-102">Capitalization Conventions</span></span>
<span data-ttu-id="14dd8-103">지침에 사용 하기 위한 간단한 방법이 장 레이아웃을 만드는 경우, 형식, 멤버 및 매개 변수를 읽기 쉽게에 대 한 확인 식별자를 일관 되 게 적용 될 때.</span><span class="sxs-lookup"><span data-stu-id="14dd8-103">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>  
  
## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="14dd8-104">식별자에 대 한 대/소문자 규칙</span><span class="sxs-lookup"><span data-stu-id="14dd8-104">Capitalization Rules for Identifiers</span></span>  
 <span data-ttu-id="14dd8-105">식별자에는 단어를 구분 하려면 식별자의 각 단어의 첫 글자를 대문자로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-105">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="14dd8-106">단어를 구분 하기 위해 밑줄을 사용 하지 않는 또는 식별자에 해당 문제에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-106">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="14dd8-107">식별자의 사용에 따라 식별자 활용할 적절 한 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-107">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>  
  
-   <span data-ttu-id="14dd8-108">PascalCasing</span><span class="sxs-lookup"><span data-stu-id="14dd8-108">PascalCasing</span></span>  
  
-   <span data-ttu-id="14dd8-109">camelCasing</span><span class="sxs-lookup"><span data-stu-id="14dd8-109">camelCasing</span></span>  
  
 <span data-ttu-id="14dd8-110">다음 예제에 나와 있는 것 처럼 매개 변수 이름 제외 하 고 모든 식별자에 사용 하는 PascalCasing 규칙 (통해의 길이 문자 2 자 약어 포함)는 각 단어의 첫 번째 문자를 대문자로 표시:</span><span class="sxs-lookup"><span data-stu-id="14dd8-110">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 <span data-ttu-id="14dd8-111">다음 식별자에 표시 된 대로 특수 한 경우 두 문자는 대문자 2 자 약어에 대 한 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-111">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>  
  
 `IOStream`  
  
 <span data-ttu-id="14dd8-112">다음 예제에 나와 있는 것 처럼 매개 변수 이름에 대해서만 사용 되는 camelCasing 규칙에 첫 번째 단어를 제외한 각 단어의 첫 번째 문자를 대문자로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-112">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="14dd8-113">또한 예제와 같이 카멜식 대/소문자를 사용 하는 식별자를 시작 하는 2 자 약어는 모두 소문자입니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-113">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 <span data-ttu-id="14dd8-114">**✓ 않습니다** PascalCasing 여러 단어로 구성 된 모든 public 멤버, 형식 및 네임 스페이스 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-114">**✓ DO** use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>  
  
 <span data-ttu-id="14dd8-115">**✓ 않습니다** camelCasing 매개 변수 이름에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-115">**✓ DO** use camelCasing for parameter names.</span></span>  
  
 <span data-ttu-id="14dd8-116">다음 표에서 다양 한 유형의 식별자에 대 한 대/소문자 규칙을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-116">The following table describes the capitalization rules for different types of identifiers.</span></span>  
  
|<span data-ttu-id="14dd8-117">식별자</span><span class="sxs-lookup"><span data-stu-id="14dd8-117">Identifier</span></span>|<span data-ttu-id="14dd8-118">대/소문자 구분</span><span class="sxs-lookup"><span data-stu-id="14dd8-118">Casing</span></span>|<span data-ttu-id="14dd8-119">예제</span><span class="sxs-lookup"><span data-stu-id="14dd8-119">Example</span></span>|  
|----------------|------------|-------------|  
|<span data-ttu-id="14dd8-120">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="14dd8-120">Namespace</span></span>|<span data-ttu-id="14dd8-121">파스칼</span><span class="sxs-lookup"><span data-stu-id="14dd8-121">Pascal</span></span>|`namespace System.Security { ... }`|  
|<span data-ttu-id="14dd8-122">형식</span><span class="sxs-lookup"><span data-stu-id="14dd8-122">Type</span></span>|<span data-ttu-id="14dd8-123">파스칼</span><span class="sxs-lookup"><span data-stu-id="14dd8-123">Pascal</span></span>|`public class StreamReader { ... }`|  
|<span data-ttu-id="14dd8-124">인터페이스</span><span class="sxs-lookup"><span data-stu-id="14dd8-124">Interface</span></span>|<span data-ttu-id="14dd8-125">파스칼</span><span class="sxs-lookup"><span data-stu-id="14dd8-125">Pascal</span></span>|`public interface IEnumerable { ... }`|  
|<span data-ttu-id="14dd8-126">메서드</span><span class="sxs-lookup"><span data-stu-id="14dd8-126">Method</span></span>|<span data-ttu-id="14dd8-127">파스칼</span><span class="sxs-lookup"><span data-stu-id="14dd8-127">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|<span data-ttu-id="14dd8-128">속성</span><span class="sxs-lookup"><span data-stu-id="14dd8-128">Property</span></span>|<span data-ttu-id="14dd8-129">파스칼</span><span class="sxs-lookup"><span data-stu-id="14dd8-129">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|<span data-ttu-id="14dd8-130">이벤트</span><span class="sxs-lookup"><span data-stu-id="14dd8-130">Event</span></span>|<span data-ttu-id="14dd8-131">파스칼</span><span class="sxs-lookup"><span data-stu-id="14dd8-131">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|<span data-ttu-id="14dd8-132">필드</span><span class="sxs-lookup"><span data-stu-id="14dd8-132">Field</span></span>|<span data-ttu-id="14dd8-133">파스칼</span><span class="sxs-lookup"><span data-stu-id="14dd8-133">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|<span data-ttu-id="14dd8-134">열거형 값</span><span class="sxs-lookup"><span data-stu-id="14dd8-134">Enum value</span></span>|<span data-ttu-id="14dd8-135">파스칼</span><span class="sxs-lookup"><span data-stu-id="14dd8-135">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|<span data-ttu-id="14dd8-136">매개 변수</span><span class="sxs-lookup"><span data-stu-id="14dd8-136">Parameter</span></span>|<span data-ttu-id="14dd8-137">카멜식 대 /</span><span class="sxs-lookup"><span data-stu-id="14dd8-137">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="14dd8-138">복합 단어 및 일반적인 용어 수익 창출</span><span class="sxs-lookup"><span data-stu-id="14dd8-138">Capitalizing Compound Words and Common Terms</span></span>  
 <span data-ttu-id="14dd8-139">대부분 복합 단어는 대/소문자의 목적을 위해 단어도 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-139">Most compound terms are treated as single words for purposes of capitalization.</span></span>  
  
 <span data-ttu-id="14dd8-140">**X 하지 않으면** 소위 닫힌 형식의 복합 단어 각 글자를 대문자로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-140">**X DO NOT** capitalize each word in so-called closed-form compound words.</span></span>  
  
 <span data-ttu-id="14dd8-141">이들은 끝점 같은 한 단어로 작성 하는 복합 단어입니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-141">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="14dd8-142">대/소문자 표기 지침이 목적으로 닫힌 형식의 복합 단어를 한 단어를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-142">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="14dd8-143">현재 사전의 사용 하 여 확인 복합 단어인 경우 닫힌 형태로 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-143">Use a current dictionary to determine if a compound word is written in closed form.</span></span>  
  
|<span data-ttu-id="14dd8-144">파스칼</span><span class="sxs-lookup"><span data-stu-id="14dd8-144">Pascal</span></span>|<span data-ttu-id="14dd8-145">카멜식 대 /</span><span class="sxs-lookup"><span data-stu-id="14dd8-145">Camel</span></span>|<span data-ttu-id="14dd8-146">not</span><span class="sxs-lookup"><span data-stu-id="14dd8-146">Not</span></span>|  
|------------|-----------|---------|  
|`BitFlag`|`bitFlag`|`Bitflag`|  
|`Callback`|`callback`|`CallBack`|  
|`Canceled`|`canceled`|`Cancelled`|  
|`DoNot`|`doNot`|`Don't`|  
|`Email`|`email`|`EMail`|  
|`Endpoint`|`endpoint`|`EndPoint`|  
|`FileName`|`fileName`|`Filename`|  
|`Gridline`|`gridline`|`GridLine`|  
|`Hashtable`|`hashtable`|`HashTable`|  
|`Id`|`id`|`ID`|  
|`Indexes`|`indexes`|`Indices`|  
|`LogOff`|`logOff`|`LogOut`|  
|`LogOn`|`logOn`|`LogIn`|  
|`Metadata`|`metadata`|`MetaData, metaData`|  
|`Multipanel`|`multipanel`|`MultiPanel`|  
|`Multiview`|`multiview`|`MultiView`|  
|`Namespace`|`namespace`|`NameSpace`|  
|`Ok`|`ok`|`OK`|  
|`Pi`|`pi`|`PI`|  
|`Placeholder`|`placeholder`|`PlaceHolder`|  
|`SignIn`|`signIn`|`SignOn`|  
|`SignOut`|`signOut`|`SignOff`|  
|`UserName`|`userName`|`Username`|  
|`WhiteSpace`|`whiteSpace`|`Whitespace`|  
|`Writable`|`writable`|`Writeable`|  
  
## <a name="case-sensitivity"></a><span data-ttu-id="14dd8-147">대/소문자 구분</span><span class="sxs-lookup"><span data-stu-id="14dd8-147">Case Sensitivity</span></span>  
 <span data-ttu-id="14dd8-148">일부 작업도 하지만 대/소문자 구분을 지원 하기 위해 CLR에서 실행할 수 있는 언어 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-148">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="14dd8-149">해당 언어에서 지 원하는 경우에 프레임 워크에 액세스할 수 있는 다른 언어는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-149">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="14dd8-150">따라서 외부에서 액세스할 수 있는 모든 Api는 동일한 컨텍스트에서 두 이름을 구별할 단독으로 사례에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-150">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>  
  
 <span data-ttu-id="14dd8-151">**X 하지 않으면** 모든 프로그래밍 언어는 대/소문자 구분 하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-151">**X DO NOT** assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="14dd8-152">그러나 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-152">They are not.</span></span> <span data-ttu-id="14dd8-153">대/소문자만 다른 이름 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14dd8-153">Names cannot differ by case alone.</span></span>  
  
 <span data-ttu-id="14dd8-154">*일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="14dd8-154">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="14dd8-155">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="14dd8-155">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14dd8-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14dd8-156">See Also</span></span>  
 [<span data-ttu-id="14dd8-157">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="14dd8-157">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="14dd8-158">명명 지침</span><span class="sxs-lookup"><span data-stu-id="14dd8-158">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
