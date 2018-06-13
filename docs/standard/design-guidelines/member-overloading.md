---
title: 멤버 오버로드
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c77f08cd573dc40083718b783ae01233ca00766
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573557"
---
# <a name="member-overloading"></a><span data-ttu-id="a68c0-102">멤버 오버로드</span><span class="sxs-lookup"><span data-stu-id="a68c0-102">Member Overloading</span></span>
<span data-ttu-id="a68c0-103">멤버 오버 로드을 같은 형식의 매개 변수 형식이 나 개수 에서만 차이가 있지만 이름이 같은 둘 이상의 멤버를 만드는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-103">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="a68c0-104">예를 들어 다음 표에 `WriteLine` 메서드가 오버 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-104">For example, in the following, the `WriteLine` method is overloaded:</span></span>  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 <span data-ttu-id="a68c0-105">메서드, 생성자 및 인덱싱된 속성 매개 변수를 사용할 수 있습니다, 때문에 해당 멤버만 오버 로드 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-105">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>  
  
 <span data-ttu-id="a68c0-106">오버 로드 사용 편의성, 생산성 및 재사용 가능한 라이브러리의 가독성을 향상 시키기 위한 가장 중요 한 기술 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-106">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="a68c0-107">매개 변수 개수에 오버 로드 하는 메서드와 생성자의 간단한 버전을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-107">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="a68c0-108">매개 변수 형식에 오버 로드 선택된 된 다양 한 종류 집합에 동일한 작업을 수행 하는 멤버에 대 한 동일한 멤버 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-108">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>  
  
 <span data-ttu-id="a68c0-109">**✓ 않습니다** 짧은 오버 로드에서 사용 되는 기본값을 나타내기 위해 설명 매개 변수 이름을 사용 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-109">**✓ DO** try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>  
  
 <span data-ttu-id="a68c0-110">**하지 말고 X** 임의의 여러 오버 로드에 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-110">**X AVOID** arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="a68c0-111">하나의 오버 로드에 매개 변수 같은 다른 오버 로드의 매개 변수 입력을 나타내는 경우 매개 변수는 이름이 같은 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-111">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>  
  
 <span data-ttu-id="a68c0-112">**하지 말고 X** 오버 로드 된 멤버의 매개 변수 순서에 일관 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-112">**X AVOID** being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="a68c0-113">같은 이름의 매개 변수는 모든 오버 로드에 동일한 위치에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-113">Parameters with the same name should appear in the same position in all overloads.</span></span>  
  
 <span data-ttu-id="a68c0-114">**✓ 않습니다** (확장 기능이 필요) 하는 경우 가상 가장 긴 오버 로드를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-114">**✓ DO** make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="a68c0-115">짧은 오버 로드는 긴 오버 로드를 통해 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-115">Shorter overloads should simply call through to a longer overload.</span></span>  
  
 <span data-ttu-id="a68c0-116">**X 하지 않으면** 사용 `ref` 또는 `out` 한정자를 멤버를 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-116">**X DO NOT** use `ref` or `out` modifiers to overload members.</span></span>  
  
 <span data-ttu-id="a68c0-117">일부 언어는 다음과 같은 오버 로드에 대 한 호출을 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-117">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="a68c0-118">또한 이러한 오버 로드 일반적으로 의미 체계가 완전히 다릅니다 아마도 아니어야 합니다 오버 로드가 있지만 별도 두 가지 방법 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-118">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>  
  
 <span data-ttu-id="a68c0-119">**X 하지 않으면** 서로 다른 의미 체계 하면서도 동일한 위치와 유사한 형식 매개 변수를 사용 하는 오버 로드를 갖고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-119">**X DO NOT** have overloads with parameters at the same position and similar types yet with different semantics.</span></span>  
  
 <span data-ttu-id="a68c0-120">**✓ 않습니다** 허용 `null` 선택적 인수를 전달 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-120">**✓ DO**  allow `null` to be passed for optional arguments.</span></span>  
  
 <span data-ttu-id="a68c0-121">**✓ 않습니다** 멤버 기본 인수가 있는 멤버를 정의 하는 대신 오버 로드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-121">**✓ DO** use member overloading rather than defining members with default arguments.</span></span>  
  
 <span data-ttu-id="a68c0-122">기본 인수는 CLS 규격이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c0-122">Default arguments are not CLS compliant.</span></span>  
  
 <span data-ttu-id="a68c0-123">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="a68c0-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a68c0-124">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="a68c0-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a68c0-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a68c0-125">See Also</span></span>  
 [<span data-ttu-id="a68c0-126">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="a68c0-126">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="a68c0-127">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="a68c0-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
