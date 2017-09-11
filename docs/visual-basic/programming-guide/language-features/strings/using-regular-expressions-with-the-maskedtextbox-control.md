---
title: "Visual Basic에서 MaskedTextBox 컨트롤과 함께 정규식 사용 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 66f61eed8bc8431392d7216ffb799b221489f332
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a><span data-ttu-id="fa856-102">Visual Basic에서 MaskedTextBox 컨트롤과 함께 정규식 사용</span><span class="sxs-lookup"><span data-stu-id="fa856-102">Using Regular Expressions with the MaskedTextBox Control in Visual Basic</span></span>
<span data-ttu-id="fa856-103">간단한 정규식에 맞게 변환 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Forms.MaskedTextBox>제어 합니다.</xref:System.Windows.Forms.MaskedTextBox></span><span class="sxs-lookup"><span data-stu-id="fa856-103">This example demonstrates how to convert simple regular expressions to work with the <xref:System.Windows.Forms.MaskedTextBox> control.</span></span>  
  
## <a name="description-of-the-masking-language"></a><span data-ttu-id="fa856-104">마스킹 언어 설명</span><span class="sxs-lookup"><span data-stu-id="fa856-104">Description of the Masking Language</span></span>  
 <span data-ttu-id="fa856-105">표준 <xref:System.Windows.Forms.MaskedTextBox>기반으로 사용 하는 마스킹 언어는 `Masked Edit` 제어 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 6.0 해당 플랫폼에서 마이그레이션하는 사용자에 잘 알고 있어야 하 고.</xref:System.Windows.Forms.MaskedTextBox></span><span class="sxs-lookup"><span data-stu-id="fa856-105">The standard <xref:System.Windows.Forms.MaskedTextBox> masking language is based on the one used by the `Masked Edit` control in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 6.0 and should be familiar to users migrating from that platform.</span></span>  
  
 <span data-ttu-id="fa856-106"><xref:System.Windows.Forms.MaskedTextBox.Mask%2A>의 속성은 <xref:System.Windows.Forms.MaskedTextBox>컨트롤 사용 하 여 입력된 마스크를 지정 합니다.</xref:System.Windows.Forms.MaskedTextBox> </xref:System.Windows.Forms.MaskedTextBox.Mask%2A></span><span class="sxs-lookup"><span data-stu-id="fa856-106">The <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property of the <xref:System.Windows.Forms.MaskedTextBox> control specifies what input mask to use.</span></span> <span data-ttu-id="fa856-107">마스크는 하나 이상의 다음 표에서 마스킹 요소로 구성 된 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-107">The mask must be a string composed of one or more of the masking elements from the following table.</span></span>  
  
|<span data-ttu-id="fa856-108">마스킹 요소</span><span class="sxs-lookup"><span data-stu-id="fa856-108">Masking element</span></span>|<span data-ttu-id="fa856-109">설명</span><span class="sxs-lookup"><span data-stu-id="fa856-109">Description</span></span>|<span data-ttu-id="fa856-110">정규식 요소</span><span class="sxs-lookup"><span data-stu-id="fa856-110">Regular expression element</span></span>|  
|---------------------|-----------------|--------------------------------|  
|<span data-ttu-id="fa856-111">0</span><span class="sxs-lookup"><span data-stu-id="fa856-111">0</span></span>|<span data-ttu-id="fa856-112">0에서 9 사이의 한 자리 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-112">Any single digit between 0 and 9.</span></span> <span data-ttu-id="fa856-113">항목이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-113">Entry required.</span></span>|<span data-ttu-id="fa856-114">\d</span><span class="sxs-lookup"><span data-stu-id="fa856-114">\d</span></span>|  
|<span data-ttu-id="fa856-115">9</span><span class="sxs-lookup"><span data-stu-id="fa856-115">9</span></span>|<span data-ttu-id="fa856-116">숫자 또는 공백이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-116">Digit or space.</span></span> <span data-ttu-id="fa856-117">선택적 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-117">Entry optional.</span></span>|<span data-ttu-id="fa856-118">[ \d]?</span><span class="sxs-lookup"><span data-stu-id="fa856-118">[ \d]?</span></span>|  
|#|<span data-ttu-id="fa856-119">숫자 또는 공백이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-119">Digit or space.</span></span> <span data-ttu-id="fa856-120">선택적 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-120">Entry optional.</span></span> <span data-ttu-id="fa856-121">이 위치에 정보를 마스크에 입력 하지 않으면 공간으로 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-121">If this position is left blank in the mask, it will be rendered as a space.</span></span> <span data-ttu-id="fa856-122">더하기 (+) 및 빼기 (-) 기호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-122">Plus (+) and minus (-) signs are allowed.</span></span>|<span data-ttu-id="fa856-123">[ \d+-]?</span><span class="sxs-lookup"><span data-stu-id="fa856-123">[ \d+-]?</span></span>|  
|<span data-ttu-id="fa856-124">L</span><span class="sxs-lookup"><span data-stu-id="fa856-124">L</span></span>|<span data-ttu-id="fa856-125">ASCII 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-125">ASCII letter.</span></span> <span data-ttu-id="fa856-126">항목이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-126">Entry required.</span></span>|<span data-ttu-id="fa856-127">[a-zA-Z]</span><span class="sxs-lookup"><span data-stu-id="fa856-127">[a-zA-Z]</span></span>|  
|<span data-ttu-id="fa856-128">?</span><span class="sxs-lookup"><span data-stu-id="fa856-128">?</span></span>|<span data-ttu-id="fa856-129">ASCII 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-129">ASCII letter.</span></span> <span data-ttu-id="fa856-130">선택적 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-130">Entry optional.</span></span>|<span data-ttu-id="fa856-131">[a-zA-Z]?</span><span class="sxs-lookup"><span data-stu-id="fa856-131">[a-zA-Z]?</span></span>|  
|&|<span data-ttu-id="fa856-132">문자.</span><span class="sxs-lookup"><span data-stu-id="fa856-132">Character.</span></span> <span data-ttu-id="fa856-133">항목이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-133">Entry required.</span></span>|<span data-ttu-id="fa856-134">[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]</span><span class="sxs-lookup"><span data-stu-id="fa856-134">[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]</span></span>|  
|<span data-ttu-id="fa856-135">C</span><span class="sxs-lookup"><span data-stu-id="fa856-135">C</span></span>|<span data-ttu-id="fa856-136">문자.</span><span class="sxs-lookup"><span data-stu-id="fa856-136">Character.</span></span> <span data-ttu-id="fa856-137">선택적 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-137">Entry optional.</span></span>|<span data-ttu-id="fa856-138">[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?</span><span class="sxs-lookup"><span data-stu-id="fa856-138">[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?</span></span>|  
|<span data-ttu-id="fa856-139">A</span><span class="sxs-lookup"><span data-stu-id="fa856-139">A</span></span>|<span data-ttu-id="fa856-140">영숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-140">Alphanumeric.</span></span> <span data-ttu-id="fa856-141">선택적 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-141">Entry optional.</span></span>|<span data-ttu-id="fa856-142">\W</span><span class="sxs-lookup"><span data-stu-id="fa856-142">\W</span></span>|  
|<span data-ttu-id="fa856-143">입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-143">.</span></span>|<span data-ttu-id="fa856-144">10 진수 자리 표시자 culture에 따른입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-144">Culture-appropriate decimal placeholder.</span></span>|<span data-ttu-id="fa856-145">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-145">Not available.</span></span>|  
|<span data-ttu-id="fa856-146">,</span><span class="sxs-lookup"><span data-stu-id="fa856-146">,</span></span>|<span data-ttu-id="fa856-147">Culture에 따른 천 단위 자리 표시자입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-147">Culture-appropriate thousands placeholder.</span></span>|<span data-ttu-id="fa856-148">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-148">Not available.</span></span>|  
|<span data-ttu-id="fa856-149">:</span><span class="sxs-lookup"><span data-stu-id="fa856-149">:</span></span>|<span data-ttu-id="fa856-150">Culture에 따른 시간 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-150">Culture-appropriate time separator.</span></span>|<span data-ttu-id="fa856-151">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-151">Not available.</span></span>|  
|/|<span data-ttu-id="fa856-152">Culture에 따른 날짜 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-152">Culture-appropriate date separator.</span></span>|<span data-ttu-id="fa856-153">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-153">Not available.</span></span>|  
|$|<span data-ttu-id="fa856-154">Culture에 따른 통화 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-154">Culture-appropriate currency symbol.</span></span>|<span data-ttu-id="fa856-155">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-155">Not available.</span></span>|  
|\<|<span data-ttu-id="fa856-156">소문자로 뒤에 있는 모든 문자를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-156">Converts all characters that follow to lowercase.</span></span>|<span data-ttu-id="fa856-157">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-157">Not available.</span></span>|  
|>|<span data-ttu-id="fa856-158">대문자로 뒤에 있는 모든 문자를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-158">Converts all characters that follow to uppercase.</span></span>|<span data-ttu-id="fa856-159">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-159">Not available.</span></span>|  
|<span data-ttu-id="fa856-160">&#124;</span><span class="sxs-lookup"><span data-stu-id="fa856-160">&#124;</span></span>|<span data-ttu-id="fa856-161">이전 shift를 실행 취소 또는 아래쪽으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-161">Undoes a previous shift up or shift down.</span></span>|<span data-ttu-id="fa856-162">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-162">Not available.</span></span>|  
|\|<span data-ttu-id="fa856-163">리터럴로 설정 마스크 문자를 이스케이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-163">Escapes a mask character, turning it into a literal.</span></span> <span data-ttu-id="fa856-164">"\\\\" 백슬래시 이스케이프 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-164">"\\\\" is the escape sequence for a backslash.</span></span>|\|  
|<span data-ttu-id="fa856-165">다른 모든 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-165">All other characters.</span></span>|<span data-ttu-id="fa856-166">리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-166">Literals.</span></span> <span data-ttu-id="fa856-167">모든 비 마스크 요소 <xref:System.Windows.Forms.MaskedTextBox>.</xref:System.Windows.Forms.MaskedTextBox> 안에 그대로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-167">All non-mask elements will appear as themselves within <xref:System.Windows.Forms.MaskedTextBox>.</span></span>|<span data-ttu-id="fa856-168">다른 모든 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-168">All other characters.</span></span>|  
  
 <span data-ttu-id="fa856-169">소수점 (.),&1;/1000 (,), 시간 (:), 날짜 (/) 및 응용 프로그램의 문화권에 의해 정의 된 대로 이러한 기호를 표시 하려면 기호 기본 통화 ($).</span><span class="sxs-lookup"><span data-stu-id="fa856-169">The decimal (.), thousandths (,), time (:), date (/), and currency ($) symbols default to displaying those symbols as defined by the application's culture.</span></span> <span data-ttu-id="fa856-170">강제로 사용 하 여 다른 문화권에 대 한 기호를 표시 하 게는 <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A>속성.</xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A></span><span class="sxs-lookup"><span data-stu-id="fa856-170">You can force them to display symbols for another culture by using the <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> property.</span></span>  
  
## <a name="regular-expressions-and-masks"></a><span data-ttu-id="fa856-171">정규식과 마스크</span><span class="sxs-lookup"><span data-stu-id="fa856-171">Regular Expressions and Masks</span></span>  
 <span data-ttu-id="fa856-172">사용자를 사용할 수 있지만 정규식과 마스크 사용자 입력 유효성 검사를 완전히 동일 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-172">Although you can use regular expressions and masks to validate user input, they are not completely equivalent.</span></span> <span data-ttu-id="fa856-173">정규식 마스크 보다 더 복잡 한 패턴을 표현할 수 있지만 더 간결 하 관련 형식으로 마스크에서 동일한 정보를 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-173">Regular expressions can express more complex patterns than masks, but masks can express the same information more succinctly and in a culturally relevant format.</span></span>  
  
 <span data-ttu-id="fa856-174">다음 표에서 각각에 대해&4; 개의 정규식과 해당 하는 마스크를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-174">The following table compares four regular expressions and the equivalent mask for each.</span></span>  
  
|<span data-ttu-id="fa856-175">정규식</span><span class="sxs-lookup"><span data-stu-id="fa856-175">Regular Expression</span></span>|<span data-ttu-id="fa856-176">마스크</span><span class="sxs-lookup"><span data-stu-id="fa856-176">Mask</span></span>|<span data-ttu-id="fa856-177">노트</span><span class="sxs-lookup"><span data-stu-id="fa856-177">Notes</span></span>|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|<span data-ttu-id="fa856-178">`/` 마스크의 문자는 논리적 날짜 구분 기호 이며 사용자에 게 응용 프로그램의 현재 문화권에 적합 한 날짜 구분 기호로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-178">The `/` character in the mask is a logical date separator, and it will appear to the user as the date separator appropriate to the application's current culture.</span></span>|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|<span data-ttu-id="fa856-179">날짜 (일, 월의 약어 및 연도) 미국 형식 뒤에 두 문자는 소문자 초기 대문자로 표시 되는 세 자리 월의 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-179">A date (day, month abbreviation, and year) in United States format in which the three-letter month abbreviation is displayed with an initial uppercase letter followed by two lowercase letters.</span></span>|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|<span data-ttu-id="fa856-180">미국 전화 번호, 지역 번호 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-180">United States phone number, area code optional.</span></span> <span data-ttu-id="fa856-181">사용자가 선택적 문자를 입력 하지 않으려는, 그녀 공백을 입력 하거나 첫 번째 0이 나타나는 마스크의 위치에 직접 마우스 포인터를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-181">If the user does not wish to enter the optional characters, she can either enter spaces or place the mouse pointer directly at the position in the mask represented by the first 0.</span></span>|  
|`$\d{6}.00`|`$999,999.00`|<span data-ttu-id="fa856-182">0-999999 사이의 통화 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-182">A currency value in the range of 0 to 999999.</span></span> <span data-ttu-id="fa856-183">통화,&1000; 단위 구분 및&10; 진수 문자는 문화권별 상응 항목으로 런타임 시 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa856-183">The currency, thousandth, and decimal characters will be replaced at run-time with their culture-specific equivalents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa856-184">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa856-184">See Also</span></span>  
 <span data-ttu-id="fa856-185"><xref:System.Windows.Forms.MaskedTextBox.Mask%2A></xref:System.Windows.Forms.MaskedTextBox.Mask%2A></span><span class="sxs-lookup"><span data-stu-id="fa856-185"><xref:System.Windows.Forms.MaskedTextBox.Mask%2A></span></span>   
 <span data-ttu-id="fa856-186"><xref:System.Windows.Forms.MaskedTextBox></xref:System.Windows.Forms.MaskedTextBox></span><span class="sxs-lookup"><span data-stu-id="fa856-186"><xref:System.Windows.Forms.MaskedTextBox></span></span>   
<span data-ttu-id="fa856-187"> [Visual Basic의 문자열 유효성 검사](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md) </span><span class="sxs-lookup"><span data-stu-id="fa856-187"> [Validating Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md) </span></span>  
<span data-ttu-id="fa856-188"> [MaskedTextBox 컨트롤](http://msdn.microsoft.com/library/235d6121-027d-481d-8d59-4f6794d15d0c)</span><span class="sxs-lookup"><span data-stu-id="fa856-188"> [MaskedTextBox Control](http://msdn.microsoft.com/library/235d6121-027d-481d-8d59-4f6794d15d0c)</span></span>
