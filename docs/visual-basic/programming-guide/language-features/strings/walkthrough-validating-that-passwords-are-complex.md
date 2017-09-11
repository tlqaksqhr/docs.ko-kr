---
title: "암호 복잡성 (Visual Basic) 유효성 검사 | Microsoft 문서"
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
- String data type, validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
caps.latest.revision: 17
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
ms.openlocfilehash: 8d636c1e43de6a108cdc217cb21aaf7689e175f7
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="14055-102">연습: 암호의 복합성 검사(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14055-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="14055-103">이 메서드는 일부 강력한 암호 특성에 대 한 검사 하 고 문자열 매개 변수 정보로 업데이트 실패에 대 한 암호를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14055-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="14055-104">암호에 사용자 권한을 부여 하는 보안 시스템에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14055-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="14055-105">그러나 암호는 권한이 없는 사용자가 추측 하기 어려운 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14055-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="14055-106">공격자가 사용할 수는 *사전 공격* 모든 사전 (또는 다른 언어로 여러 사전)에 단어를 반복 하 고 사용자의 암호로 사용 된 단어 중 하나라도 있는지 여부를 테스트 하는 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="14055-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="14055-107">"Yankees" 또는 "무스 탕"와 같은 취약 한 암호를 신속 하 게 추측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14055-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="14055-108">강력한 암호와 같은 "? 사용자 'L1N3vaFiNdMeyeP@sSWerd! ", 가능성이 훨씬 줄어듭니다 추측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14055-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="14055-109">암호로 보호 된 시스템을 사용자가 강력한 암호를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14055-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="14055-110">강력한 암호 (혼합 된 대문자, 소문자, 숫자 및 특수 문자 포함) 복잡 하며 단어 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="14055-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="14055-111">이 예제에는 복잡성을 확인 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14055-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14055-112">예제</span><span class="sxs-lookup"><span data-stu-id="14055-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="14055-113">코드</span><span class="sxs-lookup"><span data-stu-id="14055-113">Code</span></span>  
 <span data-ttu-id="14055-114">[!code-vb[VbVbcnRegEx #&1;](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="14055-114">[!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="14055-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="14055-115">Compiling the Code</span></span>  
 <span data-ttu-id="14055-116">해당 암호를 포함 하는 문자열을 전달 하 여이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="14055-116">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="14055-117">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="14055-117">This example requires:</span></span>  
  
-   <span data-ttu-id="14055-118">멤버에 대 한 액세스는 <xref:System.Text.RegularExpressions>네임 스페이스.</xref:System.Text.RegularExpressions></span><span class="sxs-lookup"><span data-stu-id="14055-118">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="14055-119">추가 `Imports` 문 코드의 멤버 이름을 정규화 하지 않는 경우.</span><span class="sxs-lookup"><span data-stu-id="14055-119">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="14055-120">자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14055-120">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="14055-121">보안</span><span class="sxs-lookup"><span data-stu-id="14055-121">Security</span></span>  
 <span data-ttu-id="14055-122">을 사용 하는 네트워크를 통해 암호를 이동 하는 경우 데이터 전송에 안전한 방법을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14055-122">If you are moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="14055-123">자세한 내용은 참조 [ASP.NET 웹 응용 프로그램 보안](https://msdn.microsoft.com/library/330a99hc)합니다.</span><span class="sxs-lookup"><span data-stu-id="14055-123">For more information, see [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).</span></span>  
  
 <span data-ttu-id="14055-124">정확도 향상 시킬 수는 `ValidatePassword` 추가 복합성 검사를 추가 하 여 함수:</span><span class="sxs-lookup"><span data-stu-id="14055-124">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
-   <span data-ttu-id="14055-125">암호 및 사용자의 이름, 사용자 id 및 응용 프로그램에서 정의 하는 사전 해당 부분 문자열을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="14055-125">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="14055-126">또한 비교를 수행할 때 동일한 것으로 시각적으로 유사한 문자를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="14055-126">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="14055-127">예를 들어, 해당 하는 숫자 "1" 및 "3"으로 문자 "l" 및 "e"를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="14055-127">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
-   <span data-ttu-id="14055-128">대 문자가 하나만 있으면 암호의 첫 문자가 아닌지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14055-128">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
-   <span data-ttu-id="14055-129">암호의 마지막 두 문자는 문자 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14055-129">Make sure that the last two characters of the password are letter characters.</span></span>  
  
-   <span data-ttu-id="14055-130">키보드의 맨 위 행에서 모든 기호는 입력 되는 암호를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14055-130">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14055-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14055-131">See Also</span></span>  
 <span data-ttu-id="14055-132"><xref:System.Text.RegularExpressions.Regex></xref:System.Text.RegularExpressions.Regex></span><span class="sxs-lookup"><span data-stu-id="14055-132"><xref:System.Text.RegularExpressions.Regex></span></span>   
<span data-ttu-id="14055-133"> [ASP.NET 웹 응용 프로그램 보안](https://msdn.microsoft.com/library/330a99hc)</span><span class="sxs-lookup"><span data-stu-id="14055-133"> [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc)</span></span>
