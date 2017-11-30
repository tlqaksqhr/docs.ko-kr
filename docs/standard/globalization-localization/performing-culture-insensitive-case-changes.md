---
title: "Culture를 구분하지 않는 대/소문자 변경 수행"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- String.ToLower method
- culture, case sensitivity
- Char.ToLower method
- case, changing in culture-insensitive strings
- Char.ToUpper method
- culture-insensitive string operations, case changes
- String.ToUpper method
- culture parameter
ms.assetid: 822d551c-c69a-4191-82f4-183d82c9179c
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c500b882c335572b8b458ba515b282e9f5362b85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-case-changes"></a><span data-ttu-id="41b3c-102">Culture를 구분하지 않는 대/소문자 변경 수행</span><span class="sxs-lookup"><span data-stu-id="41b3c-102">Performing Culture-Insensitive Case Changes</span></span>
<span data-ttu-id="41b3c-103"><xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, 및 <xref:System.Char.ToLower%2A?displayProperty=nameWithType> 메서드 매개 변수를 받지 않는 오버 로드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="41b3c-103">The <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, and <xref:System.Char.ToLower%2A?displayProperty=nameWithType> methods provide overloads that do not accept any parameters.</span></span> <span data-ttu-id="41b3c-104">기본적으로 매개 변수 없이 이러한 오버 로드는 값에 따라 대/소문자 변경 수행는 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="41b3c-104">By default, these overloads without parameters perform case changes based on the value of the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="41b3c-105">문화권에서 다를 수 있는 대/소문자 구분 결과 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="41b3c-105">This produces case-sensitive results that can vary by culture.</span></span> <span data-ttu-id="41b3c-106">명시적으로 지정 해야 하는 이러한 메서드의 오버 로드를 하 게 문화권 구분 또는 문화권을 구분 하지 않는 대/소문자 변경 여부를 명확 사용할지는 `culture` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="41b3c-106">To make it clear whether you want case changes to be culture-sensitive or culture-insensitive, you should use the overloads of these methods that require you to explicitly specify a `culture` parameter.</span></span> <span data-ttu-id="41b3c-107">문화권별 대/소문자 변경 지정 `CultureInfo.CurrentCulture` 에 대 한는 `culture` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="41b3c-107">For culture-sensitive case changes, specify `CultureInfo.CurrentCulture` for the `culture` parameter.</span></span> <span data-ttu-id="41b3c-108">문화권을 구분 하지 않는 대/소문자 변경 지정 `CultureInfo.InvariantCulture` 에 대 한는 `culture` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="41b3c-108">For culture-insensitive case changes, specify `CultureInfo.InvariantCulture` for the `culture` parameter.</span></span>  
  
 <span data-ttu-id="41b3c-109">대개 문자열 나중에 보다 쉽게 조회할 수 있도록 하지만 일반적으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41b3c-109">Often, strings are converted to a standard case to enable easier lookup later.</span></span> <span data-ttu-id="41b3c-110">문자열은 이러한 방식으로 사용 되는 경우 지정 해야 `CultureInfo.InvariantCulture` 에 대 한는 `culture` 매개 변수를 때문에 값을 <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> 소문자가 변경 되는 시간과 조회 수행 될 때 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b3c-110">When strings are used in this way, you should specify `CultureInfo.InvariantCulture` for the `culture` parameter, because the value of <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> can potentially change between the time that the case is changed and the time that the lookup occurs.</span></span>  
  
 <span data-ttu-id="41b3c-111">대/소문자 변경 작업에 따라 보안 결정을 수행 문화권을 구분 하지 않는 결과 값에 의해 영향을 받지 않도록 하려면 해야 `CultureInfo.CurrentCulture`합니다.</span><span class="sxs-lookup"><span data-stu-id="41b3c-111">If a security decision is based on a case change operation, the operation should be culture-insensitive to ensure that the result is not affected by the value of `CultureInfo.CurrentCulture`.</span></span> <span data-ttu-id="41b3c-112">"문자열 비교를 사용 하 여의 현재 문화권" 섹션을 참조는 [문자열 사용에 대 한 유용한](../../../docs/standard/base-types/best-practices-strings.md) 문화권 구분 문자열 작업을 보여 주는 예제는 일관 되지 않은 결과가 발생할 수 있습니다에 대 한 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="41b3c-112">See the "String Comparisons that Use the Current Culture" section of the [Best Practices for Using Strings](../../../docs/standard/base-types/best-practices-strings.md) article for an example that demonstrates how culture-sensitive string operations can produce inconsistent results.</span></span>  
  
## <a name="using-the-stringtoupper-and-stringtolower-methods"></a><span data-ttu-id="41b3c-113">String.ToUpper 및 String.ToLower 메서드를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="41b3c-113">Using the String.ToUpper and String.ToLower Methods</span></span>  
 <span data-ttu-id="41b3c-114">코드의 명확성에 대 한 것이 좋습니다 오버 로드를 항상 사용는 `String.ToUpper` 및 `String.ToLower` 지정할 수 있도록 하는 메서드는 `culture` 매개 변수가 명시적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="41b3c-114">For code clarity, it is recommended that you always use overloads of the `String.ToUpper` and `String.ToLower` methods that allow you to specify a `culture` parameter explicitly.</span></span> <span data-ttu-id="41b3c-115">예를 들어 다음 코드에서는 식별자 조회를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="41b3c-115">For example, the following code performs an identifier lookup.</span></span> <span data-ttu-id="41b3c-116">`key.ToLower` 작업이이 동작 하지만 기본적으로 문화권 구분 코드를 읽을 명확 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41b3c-116">The `key.ToLower` operation is culture-sensitive by default, but this behavior is not clear from reading the code.</span></span>  
  
### <a name="example"></a><span data-ttu-id="41b3c-117">예제</span><span class="sxs-lookup"><span data-stu-id="41b3c-117">Example</span></span>  
  
```vb  
Shared Function LookupKey(key As String) As Object  
   Return internalHashtable(key.ToLower())  
End Function  
```  
  
```csharp  
static object LookupKey(string key)   
{  
    return internalHashtable[key.ToLower()];  
}  
```  
  
 <span data-ttu-id="41b3c-118">원하는 경우는 `key.ToLower` 작업만을 문화권 비구분 앞의 예제를 명시적으로 사용 하려면 다음과 같이 변경 해야는 `CultureInfo.InvariantCulture` 대/소문자를 변경 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="41b3c-118">If you want the `key.ToLower` operation to be culture-insensitive, you should change the preceding example as follows to explicitly use the `CultureInfo.InvariantCulture` when changing the case.</span></span>  
  
```vb  
Shared Function LookupKey(key As String) As Object  
    Return internalHashtable(key.ToLower(CultureInfo.InvariantCulture))  
End Function  
```  
  
```csharp  
static object LookupKey(string key)   
{  
    return internalHashtable[key.ToLower(CultureInfo.InvariantCulture)];  
}  
```  
  
## <a name="using-the-chartoupper-and-chartolower-methods"></a><span data-ttu-id="41b3c-119">Char.ToUpper 및 Char.ToLower 메서드를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="41b3c-119">Using the Char.ToUpper and Char.ToLower Methods</span></span>  
 <span data-ttu-id="41b3c-120">하지만 `Char.ToUpper` 및 `Char.ToLower` 메서드에 동일한 특성을 사용할는 `String.ToUpper` 및 `String.ToLower` 터키어 (터키) 및 아제르바이잔어 (라틴 문자, 아제르바이잔) 문화권만 영향을 받는 메서드는 합니다.</span><span class="sxs-lookup"><span data-stu-id="41b3c-120">Although the `Char.ToUpper` and `Char.ToLower` methods have the same characteristics as the `String.ToUpper` and `String.ToLower` methods, the only cultures that are affected are Turkish (Turkey) and Azerbaijani (Latin, Azerbaijan).</span></span> <span data-ttu-id="41b3c-121">이들은 단일 문자의 대/소문자 차이와 두 개의 문화권입니다.</span><span class="sxs-lookup"><span data-stu-id="41b3c-121">These are the only two cultures with single-character casing differences.</span></span> <span data-ttu-id="41b3c-122">이러한 독특한 대/소문자 매핑에 대한 자세한 내용은 <xref:System.String> 클래스 항목의 "대/소문자 구분" 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="41b3c-122">For more details about this unique case mapping, see the "Casing" section in the <xref:System.String> class topic.</span></span> <span data-ttu-id="41b3c-123">코드의 명확성에 대 한 고 일관 된 결과 얻으려면 것이 좋습니다 항상 명시적으로 지정할 수 있도록 하는 이러한 메서드의 오버 로드를 사용 하는 `culture` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="41b3c-123">For code clarity and to ensure consistent results, it is recommended that you always use the overloads of these methods that allow you to explicitly specify a `culture` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41b3c-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41b3c-124">See Also</span></span>  
 <xref:System.String.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.String.ToLower%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToLower%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="41b3c-125">Culture의 영향을 받지 않는 문자열 작업 수행</span><span class="sxs-lookup"><span data-stu-id="41b3c-125">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
