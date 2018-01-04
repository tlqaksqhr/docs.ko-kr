---
title: "UriTemplate 및 UriTemplateTable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cbbe03f-4a9e-4d44-9e02-c5773239cf52
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ac77fe2c83828d2cc9473417d2b29b2d2e540923
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="uritemplate-and-uritemplatetable"></a><span data-ttu-id="41715-102">UriTemplate 및 UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="41715-102">UriTemplate and UriTemplateTable</span></span>
<span data-ttu-id="41715-103">웹 개발자는 서비스가 응답하는 URI의 셰이프 및 레이아웃을 설명할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-103">Web developers require the ability to describe the shape and layout of the URIs that their services respond to.</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="41715-104">에는 개발자가 URI를 제어할 수 있는 두 가지 새 클래스가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-104"> added two new classes to give developers control over their URIs.</span></span> <span data-ttu-id="41715-105"><xref:System.UriTemplate> 및 <xref:System.UriTemplateTable>은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 URI 기반 디스패치 엔진의 기초를 형성합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-105"><xref:System.UriTemplate> and <xref:System.UriTemplateTable> form the basis of the URI-based dispatch engine in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="41715-106">이러한 클래스를 자체적으로 사용하면 개발자가 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 구현하지 않고도 URI 매핑 메커니즘과 템플릿을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-106">These classes can also be used on their own, allowing developers to take advantage of templates and the URI mapping mechanism without implementing a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
## <a name="templates"></a><span data-ttu-id="41715-107">템플릿</span><span class="sxs-lookup"><span data-stu-id="41715-107">Templates</span></span>  
 <span data-ttu-id="41715-108">템플릿을 사용하면 상대 URI 집합을 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-108">A template is a way to describe a set of relative URIs.</span></span> <span data-ttu-id="41715-109">다음 표의 URI 템플릿 집합은 다양한 날씨 정보를 검색하는 시스템을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41715-109">The set of URI templates in the following table shows how a system that retrieves various types of weather information might be defined.</span></span>  
  
|<span data-ttu-id="41715-110">데이터</span><span class="sxs-lookup"><span data-stu-id="41715-110">Data</span></span>|<span data-ttu-id="41715-111">템플릿</span><span class="sxs-lookup"><span data-stu-id="41715-111">Template</span></span>|  
|----------|--------------|  
|<span data-ttu-id="41715-112">전국 예보</span><span class="sxs-lookup"><span data-stu-id="41715-112">National Forecast</span></span>|<span data-ttu-id="41715-113">weather/national</span><span class="sxs-lookup"><span data-stu-id="41715-113">weather/national</span></span>|  
|<span data-ttu-id="41715-114">시/도 예보</span><span class="sxs-lookup"><span data-stu-id="41715-114">State Forecast</span></span>|<span data-ttu-id="41715-115">weather/{state}</span><span class="sxs-lookup"><span data-stu-id="41715-115">weather/{state}</span></span>|  
|<span data-ttu-id="41715-116">구/군/시 예보</span><span class="sxs-lookup"><span data-stu-id="41715-116">City Forecast</span></span>|<span data-ttu-id="41715-117">weather/{state}/{city}</span><span class="sxs-lookup"><span data-stu-id="41715-117">weather/{state}/{city}</span></span>|  
|<span data-ttu-id="41715-118">활동 예보</span><span class="sxs-lookup"><span data-stu-id="41715-118">Activity Forecast</span></span>|<span data-ttu-id="41715-119">weather/{state}/{city}/{activity}</span><span class="sxs-lookup"><span data-stu-id="41715-119">weather/{state}/{city}/{activity}</span></span>|  
  
 <span data-ttu-id="41715-120">이 표에서는 구조적으로 비슷한 URI 집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41715-120">This table describes a set of structurally similar URIs.</span></span> <span data-ttu-id="41715-121">각 항목은 URI 템플릿에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-121">Each entry is a URI template.</span></span> <span data-ttu-id="41715-122">중괄호 안에 있는 세그먼트는 변수를 설명하고</span><span class="sxs-lookup"><span data-stu-id="41715-122">The segments in curly braces describe variables.</span></span> <span data-ttu-id="41715-123">중괄호 밖에 있는 세그먼트는 리터럴 문자열을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-123">The segments not in curly braces describe literal strings.</span></span> <span data-ttu-id="41715-124">개발자는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 템플릿 클래스를 사용하여 수신 URI(예: "/weather/wa/seattle/cycling")를 가져와서 해당 URI를 설명하는 템플릿("/weather/{state}/{city}/{activity}")과 일치시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-124">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] template classes allow a developer to take an incoming URI, for example, "/weather/wa/seattle/cycling", and match it to a template that describes it, "/weather/{state}/{city}/{activity}".</span></span>  
  
## <a name="uritemplate"></a><span data-ttu-id="41715-125">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="41715-125">UriTemplate</span></span>  
 <span data-ttu-id="41715-126"><xref:System.UriTemplate>은 URI 템플릿을 캡슐화하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="41715-126"><xref:System.UriTemplate> is a class that encapsulates a URI template.</span></span> <span data-ttu-id="41715-127">생성자는 템플릿을 정의하는 문자열 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-127">The constructor takes a string parameter that defines the template.</span></span> <span data-ttu-id="41715-128">이 문자열에는 다음 단원에 설명된 형식의 템플릿이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-128">This string contains the template in the format described in the next section.</span></span> <span data-ttu-id="41715-129"><xref:System.UriTemplate> 클래스는 수신 URI를 템플릿에 일치시키고, 템플릿에서 URI를 생성하고, 템플릿에 사용되는 변수 이름 컬렉션을 검색하고, 두 템플릿이 동일한지 확인하고, 템플릿의 문자열을 반환할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-129">The <xref:System.UriTemplate> class provides methods that allow you match an incoming URI to a template, generate a URI from a template, retrieve a collection of variable names used in the template, determine whether two templates are equivalent, and return the template's string.</span></span>  
  
 <span data-ttu-id="41715-130"><xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29>는 기본 주소와 후보 URI을 사용하고 URI을 템플릿에 일치시키려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-130"><xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29> takes a base address and a candidate URI and attempts to match the URI to the template.</span></span> <span data-ttu-id="41715-131">일치가 성공적으로 수행되면 <xref:System.UriTemplateMatch> 인스턴스가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="41715-131">If the match is successful, a <xref:System.UriTemplateMatch> instance is returned.</span></span> <span data-ttu-id="41715-132"><xref:System.UriTemplateMatch> 개체에는 기본 URI, 후보 URI, 쿼리 매개 변수의 이름/값 컬렉션, 상대 경로 세그먼트 배열, 일치된 변수의 이름/값 컬렉션, 일치를 수행하는 데 사용된 <xref:System.UriTemplate> 인스턴스, 후보 URI의 일치하지 않는 부분을 포함하는 문자열(템플릿에 와일드카드가 있는 경우에 사용됨) 및 템플릿에 연결된 개체 등이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-132">The <xref:System.UriTemplateMatch> object contains a base URI, the candidate URI, a name/value collection of the query parameters, an array of the relative path segments, a name/value collection of variables that were matched, the <xref:System.UriTemplate> instance used to perform the match, a string that contains any unmatched portion of the candidate URI (used when the template has a wildcard), and an object that is associated with the template.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41715-133"><xref:System.UriTemplate> 클래스는 후보 URI를 템플릿에 일치시킬 때 구성표 및 포트 번호를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-133">The <xref:System.UriTemplate> class ignores the scheme and port number when matching a candidate URI to a template.</span></span>  
  
 <span data-ttu-id="41715-134">템플릿에서 URI를 생성할 수 있게 해주는 두 메서드(<xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> 및 <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-134">There are two methods that allow you to generate a URI from a template, <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> and <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>.</span></span> <span data-ttu-id="41715-135"><xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29>은 기본 주소와 매개 변수의 이름/값 컬렉션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-135"><xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> takes a base address and a name/value collection of parameters.</span></span> <span data-ttu-id="41715-136">이러한 매개 변수는 템플릿이 바인딩될 때 변수를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-136">These parameters are substituted for variables when the template is bound.</span></span> <span data-ttu-id="41715-137"><xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>은 이름/값 쌍을 사용하고 왼쪽에서 오른쪽으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-137"><xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> takes the name/value pairs and substitutes them left to right.</span></span>  
  
 <span data-ttu-id="41715-138"><xref:System.UriTemplate.ToString>은 템플릿 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-138"><xref:System.UriTemplate.ToString> returns the template string.</span></span>  
  
 <span data-ttu-id="41715-139"><xref:System.UriTemplate.PathSegmentVariableNames%2A> 속성은 템플릿 문자열의 경로 세그먼트에 사용되는 변수 이름 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-139">The <xref:System.UriTemplate.PathSegmentVariableNames%2A> property contains a collection of the names of the variables used within path segments in the template string.</span></span>  
  
 <span data-ttu-id="41715-140"><xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29>는 <xref:System.UriTemplate>을 매개 변수로 사용하고 두 템플릿이 일치하는지 여부를 지정하는 부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-140"><xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29> takes a <xref:System.UriTemplate> as a parameter and returns a Boolean value that specifies whether the two templates are equivalent.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="41715-141"> 이 항목의 뒷부분에 나오는 템플릿 동등성.</span><span class="sxs-lookup"><span data-stu-id="41715-141"> the Template Equivalence section later in this topic.</span></span>  
  
 <span data-ttu-id="41715-142"><xref:System.UriTemplate>은 HTTP URI 문법을 따르는 모든 URI 구성표와 함께 사용되도록 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-142"><xref:System.UriTemplate> is designed to work with any URI scheme that conforms to the HTTP URI grammar.</span></span> <span data-ttu-id="41715-143">다음은 지원되는 URI 구성표의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="41715-143">The following are examples of supported URI schemes.</span></span>  
  
-   <span data-ttu-id="41715-144">http://</span><span class="sxs-lookup"><span data-stu-id="41715-144">http://</span></span>  
  
-   <span data-ttu-id="41715-145">https://</span><span class="sxs-lookup"><span data-stu-id="41715-145">https://</span></span>  
  
-   <span data-ttu-id="41715-146">net.tcp://</span><span class="sxs-lookup"><span data-stu-id="41715-146">net.tcp://</span></span>  
  
-   <span data-ttu-id="41715-147">net.pipe://</span><span class="sxs-lookup"><span data-stu-id="41715-147">net.pipe://</span></span>  
  
-   <span data-ttu-id="41715-148">sb://</span><span class="sxs-lookup"><span data-stu-id="41715-148">sb://</span></span>  
  
 <span data-ttu-id="41715-149">file:// 및 urn://와 같은 구성표는 HTTP URI 문법을 따르지 않으며 URI 템플릿과 함께 사용되면 예측할 수 없는 결과를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="41715-149">Schemes like file:// and urn:// do not conform to the HTTP URI grammar and cause unpredictable results when used with URI templates.</span></span>  
  
### <a name="template-string-syntax"></a><span data-ttu-id="41715-150">템플릿 문자열 구문</span><span class="sxs-lookup"><span data-stu-id="41715-150">Template String Syntax</span></span>  
 <span data-ttu-id="41715-151">템플릿에는 경로, 선택적 쿼리 및 선택적 조각의 세 부분이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-151">A template has three parts: a path, an optional query, and an optional fragment.</span></span> <span data-ttu-id="41715-152">예제를 보려면 다음 템플릿을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="41715-152">For an example, see the following template:</span></span>  
  
```  
"/weather/{state}/{city}?forecast={length)#frag1  
```  
  
 <span data-ttu-id="41715-153">경로는 "/weather/{state}/{city}"로 구성되고, 쿼리는 "?forecast={length}"로 구성되며, 조각은 "#frag1"로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="41715-153">The path consists of "/weather/{state}/{city}", the query consists of "?forecast={length}, and the fragment consists of "#frag1".</span></span>  
  
 <span data-ttu-id="41715-154">선행/후행 슬래시는 경로 식에서 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="41715-154">Leading and trailing slashes are optional in the path expression.</span></span> <span data-ttu-id="41715-155">쿼리 식과 조각 식 모두 완전히 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-155">Both the query and fragment expressions can be omitted entirely.</span></span> <span data-ttu-id="41715-156">경로 일련의 구분 된 세그먼트로 구성 됩니다. '/', 각 세그먼트는 리터럴 값, 변수 이름 ({중괄호}), 또는 와일드 카드를 가질 수 있습니다 (기록 '\*').</span><span class="sxs-lookup"><span data-stu-id="41715-156">A path consists of a series of segments delimited by '/', each segment can have a literal value, a variable name (written in {curly braces}), or a wildcard (written as '\*').</span></span> <span data-ttu-id="41715-157">이전 템플릿에서 "\weather\ 세그먼트는 리터럴 값이고 "{state}" 및 "{city}"는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="41715-157">In the previous template the "\weather\ segment is a literal value while "{state}" and "{city}" are variables.</span></span> <span data-ttu-id="41715-158">변수는 중괄호 안의 내용에서 해당 이름을 사용 하 고 만들려는 구체적인 값으로 바꾸어야 나중에 *닫힌 URI*합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-158">Variables take their name from the contents of their curly braces and they can later be replaced with a concrete value to create a *closed URI*.</span></span> <span data-ttu-id="41715-159">와일드 카드는 선택적 이지만 여기서 "나머지 경로" 논리적으로 일치 하는 URI의 끝에만 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-159">The wildcard is optional, but can only appear at the end of the URI, where it logically matches "the rest of the path".</span></span>  
  
 <span data-ttu-id="41715-160">쿼리 식(있는 경우)은 순서가 지정되지 않은, '&'로 구분된 이름/값 쌍을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-160">The query expression, if present, specifies a series of unordered name/value pairs delimited by '&'.</span></span> <span data-ttu-id="41715-161">쿼리 식의 요소는 리터럴 쌍(x=2) 또는 변수 쌍(x={var})이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-161">Elements of the query expression can either be literal pairs (x=2) or a variable pair (x={var}).</span></span> <span data-ttu-id="41715-162">쿼리의 오른쪽에만 변수 식을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-162">Only the right side of the query can have a variable expression.</span></span> <span data-ttu-id="41715-163">({someName} = {someValue}는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-163">({someName} = {someValue} is not allowed.</span></span> <span data-ttu-id="41715-164">짝이 없는 값(?x)은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-164">Unpaired values (?x) are not permitted.</span></span> <span data-ttu-id="41715-165">빈 쿼리 식과만 단일 구성 쿼리 식 간의 차이점이 '?' (둘 다 의미 "쿼리").</span><span class="sxs-lookup"><span data-stu-id="41715-165">There is no difference between an empty query expression and a query expression consisting of just a single '?' (both mean "any query").</span></span>  
  
 <span data-ttu-id="41715-166">조각 식은 리터럴 값으로 구성될 수 있으며 변수는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-166">The fragment expression can consist of a literal value, no variables are allowed.</span></span>  
  
 <span data-ttu-id="41715-167">템플릿 문자열 내의 모든 템플릿 변수 이름은 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-167">All template variable names within a template string must be unique.</span></span> <span data-ttu-id="41715-168">템플릿 변수 이름은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-168">Template variable names are case-insensitive.</span></span>  
  
 <span data-ttu-id="41715-169">올바른 템플릿 문자열의 예:</span><span class="sxs-lookup"><span data-stu-id="41715-169">Examples of valid template strings:</span></span>  
  
-   <span data-ttu-id="41715-170">""</span><span class="sxs-lookup"><span data-stu-id="41715-170">""</span></span>  
  
-   <span data-ttu-id="41715-171">"/shoe"</span><span class="sxs-lookup"><span data-stu-id="41715-171">"/shoe"</span></span>  
  
-   <span data-ttu-id="41715-172">"/shoe/*"</span><span class="sxs-lookup"><span data-stu-id="41715-172">"/shoe/*"</span></span>  
  
-   <span data-ttu-id="41715-173">"{shoe}/boat"</span><span class="sxs-lookup"><span data-stu-id="41715-173">"{shoe}/boat"</span></span>  
  
-   <span data-ttu-id="41715-174">"{shoe} / {보트} /bed/ {quilt}"</span><span class="sxs-lookup"><span data-stu-id="41715-174">"{shoe}/{boat}/bed/{quilt}"</span></span>  
  
-   <span data-ttu-id="41715-175">"shoe / {보트}"</span><span class="sxs-lookup"><span data-stu-id="41715-175">"shoe/{boat}"</span></span>  
  
-   <span data-ttu-id="41715-176">"shoe / {보트} / *"</span><span class="sxs-lookup"><span data-stu-id="41715-176">"shoe/{boat}/*"</span></span>  
  
-   <span data-ttu-id="41715-177">"shoe/보트? x = 2"</span><span class="sxs-lookup"><span data-stu-id="41715-177">"shoe/boat?x=2"</span></span>  
  
-   <span data-ttu-id="41715-178">"shoe / {보트}? x = {평판}"</span><span class="sxs-lookup"><span data-stu-id="41715-178">"shoe/{boat}?x={bed}"</span></span>  
  
-   <span data-ttu-id="41715-179">"shoe/{boat}?x={bed}&y=band"</span><span class="sxs-lookup"><span data-stu-id="41715-179">"shoe/{boat}?x={bed}&y=band"</span></span>  
  
-   <span data-ttu-id="41715-180">"? x = {shoe}"</span><span class="sxs-lookup"><span data-stu-id="41715-180">"?x={shoe}"</span></span>  
  
-   <span data-ttu-id="41715-181">"shoe?x=3&y={var}</span><span class="sxs-lookup"><span data-stu-id="41715-181">"shoe?x=3&y={var}</span></span>  
  
 <span data-ttu-id="41715-182">잘못된 템플릿 문자열의 예:</span><span class="sxs-lookup"><span data-stu-id="41715-182">Examples of invalid template strings:</span></span>  
  
-   <span data-ttu-id="41715-183">"{shoe} / {SHOE} / x = 2"-변수 이름이 중복 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-183">"{shoe}/{SHOE}/x=2" – Duplicate variable names.</span></span>  
  
-   <span data-ttu-id="41715-184">"{shoe} /boat/? 평판 = {shoe}"-변수 이름이 중복 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-184">"{shoe}/boat/?bed={shoe}" – Duplicate variable names.</span></span>  
  
-   <span data-ttu-id="41715-185">"? x = 2&x = 3" – 쿼리 문자열 이름/값 쌍은 리터럴인 경우에 고유 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-185">"?x=2&x=3" – Name/value pairs within a query string must be unique, even if they are literals.</span></span>  
  
-   <span data-ttu-id="41715-186">"? x = 2 &" – 쿼리 문자열의 형식이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-186">"?x=2&" – Query string is malformed.</span></span>  
  
-   <span data-ttu-id="41715-187">"? 2 2&x = {shoe}" – 쿼리 문자열 이름/값 쌍 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-187">"?2&x={shoe}" – Query string must be name/value pairs.</span></span>  
  
-   <span data-ttu-id="41715-188">"? y = 2 & & X = 3" – 쿼리 문자열은 이름/값 쌍 이어야, 이름은 '&'.</span><span class="sxs-lookup"><span data-stu-id="41715-188">"?y=2&&X=3" – Query string must be name value pairs, names cannot start with '&'.</span></span>  
  
### <a name="compound-path-segments"></a><span data-ttu-id="41715-189">복합 경로 세그먼트</span><span class="sxs-lookup"><span data-stu-id="41715-189">Compound Path Segments</span></span>  
 <span data-ttu-id="41715-190">복합 경로 세그먼트를 사용하면 단일 URI 경로 세그먼트에 여러 변수는 물론 리터럴과 함께 사용하는 변수를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-190">Compound path segments allow a single URI path segment to contain multiple variables as well as variables combined with literals.</span></span> <span data-ttu-id="41715-191">다음은 올바른 복합 경로 세그먼트의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="41715-191">The following are examples of valid compound path segments.</span></span>  
  
-   <span data-ttu-id="41715-192">/filename.{ext}/</span><span class="sxs-lookup"><span data-stu-id="41715-192">/filename.{ext}/</span></span>  
  
-   <span data-ttu-id="41715-193">/{filename}.jpg/</span><span class="sxs-lookup"><span data-stu-id="41715-193">/{filename}.jpg/</span></span>  
  
-   <span data-ttu-id="41715-194">/{filename}.{ext}/</span><span class="sxs-lookup"><span data-stu-id="41715-194">/{filename}.{ext}/</span></span>  
  
-   <span data-ttu-id="41715-195">/{a}.{b}someLiteral{c}({d})/</span><span class="sxs-lookup"><span data-stu-id="41715-195">/{a}.{b}someLiteral{c}({d})/</span></span>  
  
 <span data-ttu-id="41715-196">다음은 잘못된 경로 세그먼트의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="41715-196">The following are examples of invalid path segments.</span></span>  
  
-   <span data-ttu-id="41715-197">/{} - 변수의 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-197">/{} - Variables must be named.</span></span>  
  
-   <span data-ttu-id="41715-198">/{shoe}{boat} - 변수를 리터럴로 구분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-198">/{shoe}{boat} - Variables must be separated by a literal.</span></span>  
  
### <a name="matching-and-compound-path-segments"></a><span data-ttu-id="41715-199">복합 및 일치하는 경로 세그먼트</span><span class="sxs-lookup"><span data-stu-id="41715-199">Matching and Compound Path Segments</span></span>  
 <span data-ttu-id="41715-200">복합 경로 세그먼트를 사용하면 단일 경로 세그먼트 내에 여러 변수가 포함된 UriTemplate을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-200">Compound path segments allow you to define a UriTemplate that has multiple variables within a single path segment.</span></span> <span data-ttu-id="41715-201">다음은 템플릿 문자열의 예를 들어: "주소 / {state}. {city} "두 변수 (state 및 city)는 동일한 세그먼트 안에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-201">For example, in the following template string: "Addresses/{state}.{city}" two variables (state and city) are defined within the same segment.</span></span> <span data-ttu-id="41715-202">이 서식 파일은 "http://example.com/Washington.Redmond"과 같이 URL과 일치 하지만 "http://example.com/Washington.Redmond.Microsoft"와 같은 URL 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-202">This template would match a URL such as "http://example.com/Washington.Redmond" but it will also match an URL like "http://example.com/Washington.Redmond.Microsoft".</span></span> <span data-ttu-id="41715-203">후자의 경우 state 변수에 "Washington"이 포함 되 고 고 city 변수에 "redmond.microsoft"가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41715-203">In the latter case, the state variable will contain "Washington" and the city variable will contain "Redmond.Microsoft".</span></span> <span data-ttu-id="41715-204">이 경우 모든 텍스트(‘/’ 제외)가 {city} 변수와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-204">In this case any text (except ‘/’) will match the {city} variable.</span></span> <span data-ttu-id="41715-205">"추가" 텍스트에 일치 하지 않는 템플릿을 원하는 경우 변수 두십시오 별도 템플릿 세그먼트의 예: "주소 / {state} / {city}.</span><span class="sxs-lookup"><span data-stu-id="41715-205">If you want a template that will not match the "extra" text, place the variable in a separate template segment, for example: "Addresses/{state}/{city}.</span></span>  
  
### <a name="named-wildcard-segments"></a><span data-ttu-id="41715-206">명명된 와일드카드 세그먼트</span><span class="sxs-lookup"><span data-stu-id="41715-206">Named Wildcard Segments</span></span>  
 <span data-ttu-id="41715-207">명명된 와일드카드 세그먼트는 변수 이름이 와일드카드 문자 ‘*’로 시작하는 경로 변수 세그먼트입니다.</span><span class="sxs-lookup"><span data-stu-id="41715-207">A named wildcard segment is any path variable segment whose variable name begins with the wildcard character ‘*’.</span></span> <span data-ttu-id="41715-208">다음 템플릿 문자열에는 이름이 “shoe”인 명명된 와일드카드 세그먼트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-208">The following template string contains a named wildcard segment named "shoe".</span></span>  
  
```  
"literal/{*shoe}"  
```  
  
 <span data-ttu-id="41715-209">와일드카드 세그먼트는 다음 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-209">Wildcard segments must follow the following rules:</span></span>  
  
-   <span data-ttu-id="41715-210">각각의 템플릿 문자열에 대해서는 명명된 와일드카드 세그먼트가 최대 하나만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-210">There can be at most one named wildcard segment for each template string.</span></span>  
  
-   <span data-ttu-id="41715-211">명명된 와일드카드 세그먼트는 경로의 맨 오른쪽 세그먼트에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-211">A named wildcard segment must appear at the right-most segment in the path.</span></span>  
  
-   <span data-ttu-id="41715-212">명명된 와일드카드 세그먼트는 동일한 템플릿 문자열 내에서 익명 와일드카드 세그먼트와 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-212">A named wildcard segment cannot coexist with an anonymous wildcard segment within the same template string.</span></span>  
  
-   <span data-ttu-id="41715-213">명명된 와일드카드 세그먼트의 이름은 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-213">The name of a named wildcard segment must be unique.</span></span>  
  
-   <span data-ttu-id="41715-214">명명된 와일드카드 세그먼트는 기본값을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-214">Named wildcard segments cannot have default values.</span></span>  
  
-   <span data-ttu-id="41715-215">명명 된 와일드 카드 세그먼트로 끝날 수 없으며 "/"입니다.</span><span class="sxs-lookup"><span data-stu-id="41715-215">Named wildcard segments cannot end with "/".</span></span>  
  
### <a name="default-variable-values"></a><span data-ttu-id="41715-216">기본 변수 값</span><span class="sxs-lookup"><span data-stu-id="41715-216">Default Variable Values</span></span>  
 <span data-ttu-id="41715-217">기본 변수 값을 사용하면 템플릿 내에서 변수에 대한 기본값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-217">Default variable values allow you to specify default values for variables within a template.</span></span> <span data-ttu-id="41715-218">기본 변수는 변수를 UriTemplate 생성자에 전달된 컬렉션으로 선언하는 중괄호로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-218">Default variables can be specified with the curly braces that declare the variable or as a collection passed to the UriTemplate constructor.</span></span> <span data-ttu-id="41715-219">다음 템플릿에서는 기본값을 포함하는 변수를 사용하여 <xref:System.UriTemplate>을 지정하는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41715-219">The following template shows two ways to specify a <xref:System.UriTemplate> with variables with default values.</span></span>  
  
```  
UriTemplate t = new UriTemplate("/test/{a=1}/{b=5}");  
```  
  
 <span data-ttu-id="41715-220">이 템플릿은 기본값 `a`을 사용하여 이름이 `1`인 변수를 선언하고 기본값 `b`를 사용하여 이름이 `5`인 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-220">This template declares a variable named `a` with a default value of `1` and a variable named `b` with a default value of `5`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41715-221">경로 세그먼트 변수만 기본값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-221">Only path segment variables are allowed to have default values.</span></span> <span data-ttu-id="41715-222">쿼리 문자열 변수, 복합 세그먼트 변수 및 명명된 와일드카드 변수는 기본값을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-222">Query string variables, compound segment variables, and named wildcard variables are not permitted to have default values.</span></span>  
  
 <span data-ttu-id="41715-223">다음 코드에서는 후보 URI와 일치할 때 기본 변수 값을 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41715-223">The following code shows how default variable values are handled when matching a candidate URI.</span></span>  
  
```  
Uri baseAddress = new Uri("http://localhost:800   
Dictionary<string,string> defVals = new Dictionary<string,string> {{"a","1"}, {"b", "5"}};  
UriTemplate t = new UriTemplate("/test/{a}/{b}", defVals);0");  
UriTemplate t = new UriTemplate("/{state=WA}/{city=Redmond}/", true);  
Uri candidate = new Uri("http://localhost:8000/OR");  
  
UriTemplateMatch m1 = t.Match(baseAddress, candidate);  
  
// Display contents of BoundVariables  
foreach (string key in m1.BoundVariables.AllKeys)  
{  
    Console.WriteLine("\t\t{0}={1}", key, m1.BoundVariables[key]);  
}  
// The output of the above code is  
// Template: /{state=WA}/{city=Redmond}/  
// Candidate URI: http://localhost:8000/OR  
// BoundVariables:  
//      STATE=OR  
//       CITY=Redmond  
```  
  
> [!NOTE]
>  <span data-ttu-id="41715-224">http://localhost:8000///과 같은 URI는 위의 코드에 나열된 템플릿과 일치하지 않지만 http://localhost:8000/과 같은 URI는 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-224">A URI such as http://localhost:8000/// does not match the template listed in the preceding code, however a URI such as http://localhost:8000/ does.</span></span>  
  
 <span data-ttu-id="41715-225">다음 코드에서는 템플릿을 사용하여 URI를 만들 때 기본 변수 값을 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41715-225">The following code shows how default variable values are handled when creating a URI with a template.</span></span>  
  
```  
Uri baseAddress = new Uri("http://localhost:8000/");  
Dictionary<string,string> defVals = new Dictionary<string,string> {{"a","1"}, {"b", "5"}};  
UriTemplate t = new UriTemplate("/test/{a}/{b}", defVals);  
NameValueCollection vals = new NameValueCollection();  
vals.Add("a", "10");  
  
Uri boundUri = t.BindByName(baseAddress, vals);  
Console.WriteLine("BaseAddress: {0}", baseAddress);  
Console.WriteLine("Template: {0}", t.ToString());  
  
Console.WriteLine("Values: ");  
foreach (string key in vals.AllKeys)  
{  
    Console.WriteLine("\tKey = {0}, Value = {1}", key, vals[key]);  
}  
Console.WriteLine("Bound URI: {0}", boundUri);  
  
// The output of the preceding code is  
// BaseAddress: http://localhost:8000/  
// Template: /test/{a}/{b}  
// Values:  
//     Key = a, Value = 10  
// Bound URI: http://localhost:8000/test/10/5  
```  
  
 <span data-ttu-id="41715-226">변수에 기본값 `null`이 지정되면 약간의 추가 제약 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-226">When a variable is given a default value of `null` there are some additional constraints.</span></span> <span data-ttu-id="41715-227">템플릿 문자열의 맨 오른쪽 세그먼트 내에 변수가 포함되어 있는 경우 또는 세그먼트 오른쪽에 있는 모든 세그먼트가 기본값 `null`을 가지는 경우 변수가 기본값 `null`을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-227">A variable can have a default value of `null` if the variable is contained within the right most segment of the template string or if all segments to the right of the segment have default values of `null`.</span></span> <span data-ttu-id="41715-228">다음은 기본값이 `null`인 올바른 템플릿 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="41715-228">The following are valid template strings with default values of `null`:</span></span>  
  
-   ```  
    UriTemplate t = new UriTemplate("shoe/{boat=null}");  
    ```  
-   ```  
    UriTemplate t = new UriTemplate("{shoe=null}/{boat=null}");  
    ```  
  
-   ```  
    UriTemplate t = new UriTemplate("{shoe=1}/{boat=null}");  
    ```  
 <span data-ttu-id="41715-229">다음은 기본값이 `null`인 잘못된 템플릿 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="41715-229">The following are invalid template strings with  default values of `null`:</span></span>  
  
-   ```  
    UriTemplate t = new UriTemplate("{shoe=null}/boat"); // null default must be in the right most path segment  
    ```  
  
-   ```  
    UriTemplate t = new UriTemplate("{shoe=null}/{boat=x}/{bed=null}"); // shoe cannot have a null default because boat does not have a default null value  
    ```  
### <a name="default-values-and-matching"></a><span data-ttu-id="41715-230">기본값 및 일치</span><span class="sxs-lookup"><span data-stu-id="41715-230">Default Values and Matching</span></span>  
 <span data-ttu-id="41715-231">기본값을 가진 템플릿을 사용하여 후보 URI와 일치시킬 때 후보 URI에 값이 지정되지 않은 경우 <xref:System.UriTemplateMatch.BoundVariables%2A> 컬렉션에 기본값이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="41715-231">When matching a candidate URI with a template that has default values, the default values are placed in the <xref:System.UriTemplateMatch.BoundVariables%2A> collection if values are not specified in the candidate URI.</span></span>  
  
### <a name="template-equivalence"></a><span data-ttu-id="41715-232">템플릿 동등성</span><span class="sxs-lookup"><span data-stu-id="41715-232">Template Equivalence</span></span>  
 <span data-ttu-id="41715-233">두 서식 파일에 있다고 *구조적으로 동등* 때 템플릿 리터럴 모두 일치 하 고 동일한 세그먼트에 변수가 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-233">Two templates are said to be *structurally equivalent* when all of the templates' literals match and they have variables in the same segments.</span></span> <span data-ttu-id="41715-234">예를 들어 다음 템플릿은 구조적으로 동등합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-234">For example the following templates are structurally equivalent:</span></span>  
  
-   <span data-ttu-id="41715-235">/a/{var1}/b b/{var2}?x=1&y=2</span><span class="sxs-lookup"><span data-stu-id="41715-235">/a/{var1}/b b/{var2}?x=1&y=2</span></span>  
  
-   <span data-ttu-id="41715-236">a/{x}/b%20b/{var1}?y=2&x=1</span><span class="sxs-lookup"><span data-stu-id="41715-236">a/{x}/b%20b/{var1}?y=2&x=1</span></span>  
  
-   <span data-ttu-id="41715-237">a/{y}/B%20B/{z}/?y=2&x=1</span><span class="sxs-lookup"><span data-stu-id="41715-237">a/{y}/B%20B/{z}/?y=2&x=1</span></span>  
  
 <span data-ttu-id="41715-238">다음 몇 가지 사항에 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-238">A few things to notice:</span></span>  
  
-   <span data-ttu-id="41715-239">템플릿에 선행 슬래시가 있는 경우 첫 번째 슬래시만 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="41715-239">If a template contains leading slashes, only the first one is ignored.</span></span>  
  
-   <span data-ttu-id="41715-240">템플릿 문자열의 구조적 동등성을 비교할 때 변수 이름과 경로 세그먼트의 대/소문자는 무시되고, 쿼리 문자열의 대/소문자는 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="41715-240">When comparing template strings for structural equivalence, case is ignored for variable names and path segments, query strings are case sensitive.</span></span>  
  
-   <span data-ttu-id="41715-241">쿼리 문자열은 순서가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-241">Query strings are unordered.</span></span>  
  
## <a name="uritemplatetable"></a><span data-ttu-id="41715-242">UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="41715-242">UriTemplateTable</span></span>  
 <span data-ttu-id="41715-243"><xref:System.UriTemplateTable> 클래스는 개발자의 선택 개체에 바인딩된 <xref:System.UriTemplate> 개체의 연결 테이블을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="41715-243">The <xref:System.UriTemplateTable> class represents an associative table of <xref:System.UriTemplate> objects bound to an object of the developer's choosing.</span></span> <span data-ttu-id="41715-244"><xref:System.UriTemplateTable>를 호출하기 전에 <xref:System.UriTemplate>에 하나 이상의 <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-244">A <xref:System.UriTemplateTable> must contain at least one <xref:System.UriTemplate> prior to calling <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span></span> <span data-ttu-id="41715-245"><xref:System.UriTemplateTable>가 호출되기 이전에는 <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>의 내용을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-245">The contents of a <xref:System.UriTemplateTable> can be changed until <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called.</span></span> <span data-ttu-id="41715-246"><xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>가 호출되면 유효성 검사가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="41715-246">Validation is performed when <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called.</span></span> <span data-ttu-id="41715-247">수행되는 유효성 검사 형식은 `allowMultiple`에 대한 <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> 매개 변수 값에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="41715-247">The type of validation performed depends upon the value of the `allowMultiple` parameter to <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span></span>  
  
 <span data-ttu-id="41715-248"><xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>를 전달하여 `false`를 호출하면 <xref:System.UriTemplateTable>에서 테이블에 템플릿이 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-248">When <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called passing in `false`, the <xref:System.UriTemplateTable> checks to make sure there are no templates in the table.</span></span> <span data-ttu-id="41715-249">구조적으로 동등한 템플릿이 있으면 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-249">If it finds any structurally equivalent templates, it throws an exception.</span></span> <span data-ttu-id="41715-250">하나의 템플릿만 수신 URI와 일치하게 하려면 <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29>과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-250">This is used in conjunction with <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29> when you want to ensure only one template matches an incoming URI.</span></span>  
  
 <span data-ttu-id="41715-251"><xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>를 전달하여 `true`를 호출하면 <xref:System.UriTemplateTable>에서 <xref:System.UriTemplateTable>에 구조적으로 동등한 여러 템플릿을 포함하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-251">When <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called passing in `true`, <xref:System.UriTemplateTable> allows multiple, structurally-equivalent templates to be contained within a <xref:System.UriTemplateTable>.</span></span>  
  
 <span data-ttu-id="41715-252"><xref:System.UriTemplate>에 추가된 <xref:System.UriTemplateTable> 개체 집합에 쿼리 문자열이 있는 경우 해당 문자열은 모호하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-252">If a set of <xref:System.UriTemplate> objects added to a <xref:System.UriTemplateTable> contain query strings they must not be ambiguous.</span></span> <span data-ttu-id="41715-253">동일한 쿼리 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-253">Identical query strings are allowed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41715-254"><xref:System.UriTemplateTable>에서 HTTP가 아닌 구성표를 사용하는 기본 주소를 허용하는 동안 후보 URI를 템플릿에 일치시킬 때 구성표 및 포트 번호가 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="41715-254">While the <xref:System.UriTemplateTable> allows base addresses that use schemes other than HTTP, the scheme and port number are ignored when matching candidate URIs to templates.</span></span>  
  
### <a name="query-string-ambiguity"></a><span data-ttu-id="41715-255">쿼리 문자열 모호성</span><span class="sxs-lookup"><span data-stu-id="41715-255">Query String Ambiguity</span></span>  
 <span data-ttu-id="41715-256">동일한 경로를 공유하는 템플릿은 여러 템플릿과 일치하는 URI가 있을 경우 모호한 쿼리 문자열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-256">Templates that share an equivalent path contain ambiguous query strings if there is a URI that matches more than one template.</span></span>  
  
 <span data-ttu-id="41715-257">다음 쿼리 문자열 집합은 모호하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41715-257">The following sets of query strings are unambiguous within themselves:</span></span>  
  
-   <span data-ttu-id="41715-258">?x=1</span><span class="sxs-lookup"><span data-stu-id="41715-258">?x=1</span></span>  
  
-   <span data-ttu-id="41715-259">?x=2</span><span class="sxs-lookup"><span data-stu-id="41715-259">?x=2</span></span>  
  
-   <span data-ttu-id="41715-260">?x=3</span><span class="sxs-lookup"><span data-stu-id="41715-260">?x=3</span></span>  
  
-   <span data-ttu-id="41715-261">?x=1&y={var}</span><span class="sxs-lookup"><span data-stu-id="41715-261">?x=1&y={var}</span></span>  
  
-   <span data-ttu-id="41715-262">?x=2&z={var}</span><span class="sxs-lookup"><span data-stu-id="41715-262">?x=2&z={var}</span></span>  
  
-   <span data-ttu-id="41715-263">?x=3</span><span class="sxs-lookup"><span data-stu-id="41715-263">?x=3</span></span>  
  
-   <span data-ttu-id="41715-264">?x=1</span><span class="sxs-lookup"><span data-stu-id="41715-264">?x=1</span></span>  
  
-   <span data-ttu-id="41715-265">?</span><span class="sxs-lookup"><span data-stu-id="41715-265">?</span></span>  
  
-   <span data-ttu-id="41715-266">?</span><span class="sxs-lookup"><span data-stu-id="41715-266">?</span></span> <span data-ttu-id="41715-267">x={var}</span><span class="sxs-lookup"><span data-stu-id="41715-267">x={var}</span></span>  
  
-   <span data-ttu-id="41715-268">?</span><span class="sxs-lookup"><span data-stu-id="41715-268">?</span></span>  
  
-   <span data-ttu-id="41715-269">?m=get&c=rss</span><span class="sxs-lookup"><span data-stu-id="41715-269">?m=get&c=rss</span></span>  
  
-   <span data-ttu-id="41715-270">?m=put&c=rss</span><span class="sxs-lookup"><span data-stu-id="41715-270">?m=put&c=rss</span></span>  
  
-   <span data-ttu-id="41715-271">?m=get&c=atom</span><span class="sxs-lookup"><span data-stu-id="41715-271">?m=get&c=atom</span></span>  
  
-   <span data-ttu-id="41715-272">?m=put&c=atom</span><span class="sxs-lookup"><span data-stu-id="41715-272">?m=put&c=atom</span></span>  
  
 <span data-ttu-id="41715-273">다음 쿼리 문자열 템플릿 집합은 모호합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-273">The following sets of query string templates are ambiguous within themselves:</span></span>  
  
-   <span data-ttu-id="41715-274">?x=1</span><span class="sxs-lookup"><span data-stu-id="41715-274">?x=1</span></span>  
  
-   <span data-ttu-id="41715-275">?x={var}</span><span class="sxs-lookup"><span data-stu-id="41715-275">?x={var}</span></span>  
  
 <span data-ttu-id="41715-276">"x=1" - 두 템플릿 모두와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-276">"x=1" - Matches both templates.</span></span>  
  
-   <span data-ttu-id="41715-277">?x=1</span><span class="sxs-lookup"><span data-stu-id="41715-277">?x=1</span></span>  
  
-   <span data-ttu-id="41715-278">?y=2</span><span class="sxs-lookup"><span data-stu-id="41715-278">?y=2</span></span>  
  
 <span data-ttu-id="41715-279">"x=1&y=2"는 두 템플릿 모두와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-279">"x=1&y=2" matches both templates.</span></span> <span data-ttu-id="41715-280">쿼리 문자열이 일치하는 템플릿보다 더 많은 쿼리 문자열 변수를 포함할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="41715-280">This is because a query string may contain more query string variables then the template it matches.</span></span>  
  
-   <span data-ttu-id="41715-281">?x=1</span><span class="sxs-lookup"><span data-stu-id="41715-281">?x=1</span></span>  
  
-   <span data-ttu-id="41715-282">?x=1&y={var}</span><span class="sxs-lookup"><span data-stu-id="41715-282">?x=1&y={var}</span></span>  
  
 <span data-ttu-id="41715-283">"x=1&y=3"은 두 템플릿 모두와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="41715-283">"x=1&y=3" matches both templates.</span></span>  
  
-   <span data-ttu-id="41715-284">?x=3&y=4</span><span class="sxs-lookup"><span data-stu-id="41715-284">?x=3&y=4</span></span>  
  
-   <span data-ttu-id="41715-285">?x=3&z=5</span><span class="sxs-lookup"><span data-stu-id="41715-285">?x=3&z=5</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41715-286">문자 á와 Á는 URI 경로 또는 <xref:System.UriTemplate> 경로 세그먼트 리터럴에 표시될 경우 서로 다른 문자로 간주됩니다. 그러나 문자 a와 A는 동일한 문자로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="41715-286">The characters á and Á are considered to be different characters when they appear as part of a URI path or <xref:System.UriTemplate> path segment literal (but the characters a and A are considered to be the same).</span></span> <span data-ttu-id="41715-287">문자 á와 Á는 <xref:System.UriTemplate> {variableName} 또는 쿼리 문자열에 표시될 경우 동일한 문자로 간주됩니다. a와 A도 동일한 문자로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="41715-287">The characters á and Á are considered to be the same characters when they appear as part of a <xref:System.UriTemplate> {variableName} or a query string (and a and A are also considered to be the same characters).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41715-288">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41715-288">See Also</span></span>  
 [<span data-ttu-id="41715-289">WCF 웹 HTTP 프로그래밍 모델 개요</span><span class="sxs-lookup"><span data-stu-id="41715-289">WCF Web HTTP Programming Model Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)  
 [<span data-ttu-id="41715-290">WCF 웹 HTTP 프로그래밍 개체 모델</span><span class="sxs-lookup"><span data-stu-id="41715-290">WCF Web HTTP Programming Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)  
 [<span data-ttu-id="41715-291">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="41715-291">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)  
 [<span data-ttu-id="41715-292">UriTemplate 테이블</span><span class="sxs-lookup"><span data-stu-id="41715-292">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [<span data-ttu-id="41715-293">UriTemplate 테이블 디스패처</span><span class="sxs-lookup"><span data-stu-id="41715-293">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
