---
title: "정규식 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8f24694-49db-4339-92ec-014e3d4ae63b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3d40d33a5d93ecce07a2e264dcfe9fcde3778437
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="regular-expression-activities"></a><span data-ttu-id="03e22-102">정규식 활동</span><span class="sxs-lookup"><span data-stu-id="03e22-102">Regular Expression Activities</span></span>
<span data-ttu-id="03e22-103">이 샘플에서는 <xref:System.Text.RegularExpressions> 네임스페이스의 정규식 기능을 노출하는 활동 집합을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-103">This sample demonstrates how to create a set of activities that expose the regular expression functionality of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="03e22-104">이러한 사용자 지정 활동은 워크플로 응용 프로그램 내에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-104">These custom activities can be used within a workflow application.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="03e22-105">정규식, 참조 [N:System.Text.RegularExpressions](http://go.microsoft.com/fwlink/?LinkId=150434) Namespace입니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-105"> regular expressions, see [N:System.Text.RegularExpressions](http://go.microsoft.com/fwlink/?LinkId=150434) Namespace.</span></span>  
  
 <span data-ttu-id="03e22-106">다음 표에는 이 샘플의 사용자 지정 활동에 대한 자세한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-106">The following table details the custom activities in this sample.</span></span>  
  
|<span data-ttu-id="03e22-107">동작</span><span class="sxs-lookup"><span data-stu-id="03e22-107">Activity</span></span>|<span data-ttu-id="03e22-108">설명</span><span class="sxs-lookup"><span data-stu-id="03e22-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="03e22-109">IsMatch</span><span class="sxs-lookup"><span data-stu-id="03e22-109">IsMatch</span></span>|<span data-ttu-id="03e22-110">입력 문자열에서 정규식에 일치하는 항목을 찾았는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-110">Specifies whether the regular expression found a match in the input string.</span></span>|  
|<span data-ttu-id="03e22-111">요청 내용</span><span class="sxs-lookup"><span data-stu-id="03e22-111">Matches</span></span>|<span data-ttu-id="03e22-112">입력 문자열에서 정규식의 모든 항목을 검색하고 일치하는 항목을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-112">Searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span>|  
|<span data-ttu-id="03e22-113">Replace</span><span class="sxs-lookup"><span data-stu-id="03e22-113">Replace</span></span>|<span data-ttu-id="03e22-114">지정된 입력 문자열 내에서 정규식 패턴에 일치하는 문자열을 지정된 대체 문자열로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-114">Within a specified input string, replaces strings that match a regular expression pattern with a specified replacement string.</span></span>|  
  
## <a name="ismatch"></a><span data-ttu-id="03e22-115">IsMatch</span><span class="sxs-lookup"><span data-stu-id="03e22-115">IsMatch</span></span>  
 <span data-ttu-id="03e22-116">`IsMatch` 사용자 지정 활동은 `true` 문자열 속성에서 `Input` 속성에 지정된 정규식에 일치하는 항목을 찾은 경우 `Pattern`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-116">The `IsMatch` custom activity returns `true` if the `Input` string property finds a match in the regular expression specified in the `Pattern` property.</span></span> <span data-ttu-id="03e22-117">이 활동은 <xref:System.Activities.CodeActivity%601>에서 파생되며 <xref:System.Activities.CodeActivity%601.Execute%2A> 메서드 내에서 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-117">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method.</span></span>  
  
 <span data-ttu-id="03e22-118">다음 표에서는 `IsMatch` 사용자 지정 활동의 속성과 반환 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-118">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="03e22-119">속성 또는 반환 값</span><span class="sxs-lookup"><span data-stu-id="03e22-119">Property or Return Value</span></span>|<span data-ttu-id="03e22-120">설명</span><span class="sxs-lookup"><span data-stu-id="03e22-120">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="03e22-121">Pattern(필수)</span><span class="sxs-lookup"><span data-stu-id="03e22-121">Pattern (required)</span></span>|<span data-ttu-id="03e22-122">검색에 사용할 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-122">The regular expression to search with.</span></span>|  
|<span data-ttu-id="03e22-123">Input(필수)</span><span class="sxs-lookup"><span data-stu-id="03e22-123">Input (required)</span></span>|<span data-ttu-id="03e22-124">검색할 입력 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-124">The input string to search.</span></span>|  
|<span data-ttu-id="03e22-125">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="03e22-125">RegexOptions</span></span>|<span data-ttu-id="03e22-126">비트 OR 조합 [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-126">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="03e22-127">반환 값</span><span class="sxs-lookup"><span data-stu-id="03e22-127">Return value</span></span>|<span data-ttu-id="03e22-128">제공된 패턴에 일치하는 항목을 입력에서 찾으면 `true`이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-128">`true` if the input finds a match in the provided pattern; otherwise `false`.</span></span>|  
  
 <span data-ttu-id="03e22-129">다음 코드 예제에서는 `IsMatch` 사용자 지정 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-129">The following code example demonstrates how to use the `IsMatch` custom activity.</span></span>  
  
```  
new IsMatch  
{  
    Pattern = new InArgument<string>( @"^-?\d+(\.\d{2})?$"),  
    Input = "20.00",  
};  
```  
  
## <a name="matches"></a><span data-ttu-id="03e22-130">요청 내용</span><span class="sxs-lookup"><span data-stu-id="03e22-130">Matches</span></span>  
 <span data-ttu-id="03e22-131">`Matches` 사용자 지정 활동은 입력 문자열에서 정규식의 모든 항목을 검색하고 일치하는 항목을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-131">The `Matches` custom activity searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span> <span data-ttu-id="03e22-132">이 활동은 <xref:System.Activities.CodeActivity%601>에서 파생되며 <xref:System.Activities.CodeActivity%601.Execute%2A> 메서드 내에서 <xref:System.Text.RegularExpressions.Regex.Matches%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-132">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Matches%2A> method.</span></span>  
  
 <span data-ttu-id="03e22-133">다음 표에서는 `IsMatch` 사용자 지정 활동의 속성과 반환 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-133">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="03e22-134">속성 또는 반환 값</span><span class="sxs-lookup"><span data-stu-id="03e22-134">Property or Return Value</span></span>|<span data-ttu-id="03e22-135">설명</span><span class="sxs-lookup"><span data-stu-id="03e22-135">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="03e22-136">Pattern(필수)</span><span class="sxs-lookup"><span data-stu-id="03e22-136">Pattern (required)</span></span>|<span data-ttu-id="03e22-137">검색에 사용할 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-137">The regular expression to search with.</span></span>|  
|<span data-ttu-id="03e22-138">Input(필수)</span><span class="sxs-lookup"><span data-stu-id="03e22-138">Input (required)</span></span>|<span data-ttu-id="03e22-139">검색할 입력 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-139">The input string to search.</span></span>|  
|<span data-ttu-id="03e22-140">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="03e22-140">RegexOptions</span></span>|<span data-ttu-id="03e22-141">비트 OR 조합 [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-141">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="03e22-142">반환 값</span><span class="sxs-lookup"><span data-stu-id="03e22-142">Return Value</span></span>|<span data-ttu-id="03e22-143">일치하는 항목의 컬렉션이 포함된 <xref:System.Text.RegularExpressions.MatchCollection>입니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-143">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="03e22-144">다음 코드 예제에서는 `Matches` 사용자 지정 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-144">The following code example demonstrates how to use the `Matches` custom activity.</span></span>  
  
```  
new Matches  
{  
    Pattern = @"\b(?<word>\w+)\s+(\k<word>)\b",  
    Input = "The quick brown fox  fox jumped over over the lazy dog dog.",  
};  
```  
  
## <a name="replace"></a><span data-ttu-id="03e22-145">Replace</span><span class="sxs-lookup"><span data-stu-id="03e22-145">Replace</span></span>  
 <span data-ttu-id="03e22-146">`Replace` 사용자 지정 활동은 입력 문자열을 검색하고 지정된 정규식에 일치하는 모든 문자열을 대체 문자열로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-146">The `Replace` custom activity searches an input string and replaces all strings that match a specified regular expression with a string.</span></span> <span data-ttu-id="03e22-147">이 활동은 <xref:System.Activities.CodeActivity%601>에서 파생되며 <xref:System.Activities.CodeActivity%601.Execute%2A> 메서드 내에서 <xref:System.Text.RegularExpressions.Regex.Replace%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-147">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Replace%2A> method.</span></span>  
  
 <span data-ttu-id="03e22-148">다음 표에서는 `Replace` 사용자 지정 활동의 속성과 반환 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-148">The following table describes the properties and return value for the `Replace` custom activity.</span></span>  
  
|<span data-ttu-id="03e22-149">속성 또는 반환 값</span><span class="sxs-lookup"><span data-stu-id="03e22-149">Property or Return Value</span></span>|<span data-ttu-id="03e22-150">설명</span><span class="sxs-lookup"><span data-stu-id="03e22-150">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="03e22-151">Pattern(필수)</span><span class="sxs-lookup"><span data-stu-id="03e22-151">Pattern (required)</span></span>|<span data-ttu-id="03e22-152">검색에 사용할 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-152">The regular expression to search with.</span></span>|  
|<span data-ttu-id="03e22-153">Input(필수)</span><span class="sxs-lookup"><span data-stu-id="03e22-153">Input (required)</span></span>|<span data-ttu-id="03e22-154">검색할 입력 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-154">The input string to search.</span></span>|  
|<span data-ttu-id="03e22-155">Replacement</span><span class="sxs-lookup"><span data-stu-id="03e22-155">Replacement</span></span>|<span data-ttu-id="03e22-156">대체 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-156">The replacement string.</span></span><br /><br /> <span data-ttu-id="03e22-157">`Replacement`를 지정한 경우 `MatchEvaluator` 속성이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-157">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="03e22-158">`Replacement` 또는 `MatchEvaluator` 속성 중 하나는 반드시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-158">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="03e22-159">MatchEvaluator</span><span class="sxs-lookup"><span data-stu-id="03e22-159">MatchEvaluator</span></span>|<span data-ttu-id="03e22-160">각 항목의 일치 여부를 조사하고 원래 일치 문자열 또는 대체 문자열을 반환하는 사용자 지정 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-160">A custom method that examines each match and returns either the original matched string or a replacement string.</span></span><br /><br /> <span data-ttu-id="03e22-161">`Replacement`를 지정한 경우 `MatchEvaluator` 속성이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-161">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="03e22-162">`Replacement` 또는 `MatchEvaluator` 속성 중 하나는 반드시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-162">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="03e22-163">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="03e22-163">RegexOptions</span></span>|<span data-ttu-id="03e22-164">비트 OR 조합 [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-164">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="03e22-165">반환 값</span><span class="sxs-lookup"><span data-stu-id="03e22-165">Return Value</span></span>|<span data-ttu-id="03e22-166">일치하는 항목의 컬렉션이 포함된 <xref:System.Text.RegularExpressions.MatchCollection>입니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-166">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="03e22-167">다음 코드 예제에서는 `Replace` 사용자 지정 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-167">The following code example demonstrates how to use the `Replace` custom activity.</span></span>  
  
```  
// Using the replacement string.  
new Replace  
{  
    Pattern = @"\bWorld\b",  
    Input = "Hello World! This is a wonderful World",  
    Replacement = "Universe"  
};  
  
// Using a match evaluator.  
new Replace  
{  
    Pattern = new InArgument<string>(pattern),  
    Input = new InArgument<string>(input),  
    MatchEvaluator = new MatchEvaluator(CapText)                  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="03e22-168">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="03e22-168">To use this sample</span></span>  
  
1.  <span data-ttu-id="03e22-169">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 RegexActivities.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-169">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RegexActivities.sln solution file.</span></span>  
  
2.  <span data-ttu-id="03e22-170">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-170">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="03e22-171">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-171">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="03e22-172">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-172">The samples may already be installed on your machine.</span></span> <span data-ttu-id="03e22-173">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="03e22-173">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="03e22-174">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="03e22-174">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="03e22-175">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e22-175">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Regex`