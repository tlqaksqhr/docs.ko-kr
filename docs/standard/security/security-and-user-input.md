---
title: "보안 및 사용자 입력"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [.NET Framework], user input
- user input, security
- secure coding, user input
- code security, user input
ms.assetid: 9141076a-96c9-4b01-93de-366bb1d858bc
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 804b91cdda1316bc0a3081c8353493faf8869b4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="security-and-user-input"></a><span data-ttu-id="1c9ac-102">보안 및 사용자 입력</span><span class="sxs-lookup"><span data-stu-id="1c9ac-102">Security and User Input</span></span>
<span data-ttu-id="1c9ac-103">웹 요청 또는 URL에서 받은 데이터와 Microsoft Windows Forms 응용 프로그램의 컨트롤에 대한 입력 등을 포함하여 모든 종류의 사용자 입력 데이터는 다른 코드를 호출하는 매개 변수로 직접 사용되는 경우가 많기 때문에 코드에 악영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9ac-103">User data, which is any kind of input (data from a Web request or URL, input to controls of a Microsoft Windows Forms application, and so on), can adversely influence code because often that data is used directly as parameters to call other code.</span></span> <span data-ttu-id="1c9ac-104">이런 상황은 이상한 매개 변수로 코드를 호출하는 악성 코드의 경우와 비슷하므로 같은 예방 조치를 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9ac-104">This situation is analogous to malicious code calling your code with strange parameters, and the same precautions should be taken.</span></span> <span data-ttu-id="1c9ac-105">사용자 입력의 경우 신뢰할 수 없는 데이터가 있는지 여부를 추적하기 위한 스택 프레임이 없기 때문에 안전을 보장하기가 더 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9ac-105">User input is actually harder to make safe because there is no stack frame to trace the presence of the potentially untrusted data.</span></span>  
  
 <span data-ttu-id="1c9ac-106">이러한 문제는 보안과 관련이 없어 보이는 코드에 존재할 수 있지만 실제로는 다른 코드로 올바르지 않은 데이터를 전달하는 통로가 되므로 발견하기가 가장 미묘하고 어려운 보안 버그에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9ac-106">These are among the subtlest and hardest security bugs to find because, although they can exist in code that is seemingly unrelated to security, they are a gateway to pass bad data through to other code.</span></span> <span data-ttu-id="1c9ac-107">이러한 버그를 찾으려면 모든 유형의 입력 데이터를 따라가면서 가능한 값의 범위가 될 수 있는 것을 생각해 보고 해당 데이터를 받는 코드가 이 모든 경우를 처리할 수 있는지 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9ac-107">To look for these bugs, follow any kind of input data, imagine what the range of possible values might be, and consider whether the code seeing this data can handle all those cases.</span></span> <span data-ttu-id="1c9ac-108">범위를 검사하고 코드가 처리할 수 없는 입력을 거부하면 이러한 버그를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9ac-108">You can fix these bugs through range checking and rejecting any input the code cannot handle.</span></span>  
  
 <span data-ttu-id="1c9ac-109">사용자 데이터와 관련된 중요한 고려 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9ac-109">Some important considerations involving user data include the following:</span></span>  
  
-   <span data-ttu-id="1c9ac-110">서버 응답에 있는 모든 사용자 데이터는 클라이언트 쪽의 서버 사이트 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9ac-110">Any user data in a server response runs in the context of the server's site on the client.</span></span> <span data-ttu-id="1c9ac-111">웹 서버가 사용자 데이터를 가져와서 반환된 웹 페이지에 삽입하는 경우 사용자 데이터는 **\<script>** 태그를 포함할 수도 있으며 서버에서 실행되는 것처럼 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9ac-111">If your Web server takes user data and inserts it into the returned Web page, it might, for example, include a **\<script>** tag and run as if from the server.</span></span>  
  
-   <span data-ttu-id="1c9ac-112">클라이언트는 어떤 URL이라도 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9ac-112">Remember that the client can request any URL.</span></span>  
  
-   <span data-ttu-id="1c9ac-113">다음과 같이 복잡하거나 잘못된 경로를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="1c9ac-113">Consider tricky or invalid paths:</span></span>  
  
    -   <span data-ttu-id="1c9ac-114">..\ , 매우 긴 경로</span><span class="sxs-lookup"><span data-stu-id="1c9ac-114">..\ , extremely long paths.</span></span>  
  
    -   <span data-ttu-id="1c9ac-115">와일드카드 문자(*)의 사용</span><span class="sxs-lookup"><span data-stu-id="1c9ac-115">Use of wild card characters (*).</span></span>  
  
    -   <span data-ttu-id="1c9ac-116">토큰 확장(%토큰%)</span><span class="sxs-lookup"><span data-stu-id="1c9ac-116">Token expansion (%token%).</span></span>  
  
    -   <span data-ttu-id="1c9ac-117">특별한 의미가 있는 이상한 형식의 경로</span><span class="sxs-lookup"><span data-stu-id="1c9ac-117">Strange forms of paths with special meaning.</span></span>  
  
    -   <span data-ttu-id="1c9ac-118">특별한 의미가 있는 이상한 형식의 경로(예: `filename::$DATA`)</span><span class="sxs-lookup"><span data-stu-id="1c9ac-118">Alternate file system stream names such as `filename::$DATA`.</span></span>  
  
    -   <span data-ttu-id="1c9ac-119">짧은 파일 이름(예: `longfilename`의 경우 `longfi~1`)</span><span class="sxs-lookup"><span data-stu-id="1c9ac-119">Short versions of file names such as `longfi~1` for `longfilename`.</span></span>  
  
-   <span data-ttu-id="1c9ac-120">Eval(userdata)은 어떤 작업이든 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9ac-120">Remember that Eval(userdata) can do anything.</span></span>  
  
-   <span data-ttu-id="1c9ac-121">런타임에 일부 사용자 데이터를 포함하는 이름에 바인딩하는 것을 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="1c9ac-121">Be wary of late binding to a name that includes some user data.</span></span>  
  
-   <span data-ttu-id="1c9ac-122">웹 데이터를 처리하는 경우에는 다음과 같이 허용 가능한 다양한 형식의 이스케이프를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="1c9ac-122">If you are dealing with Web data, consider the various forms of escapes that are permissible, including:</span></span>  
  
    -   <span data-ttu-id="1c9ac-123">16진수 이스케이프(%nn)</span><span class="sxs-lookup"><span data-stu-id="1c9ac-123">Hexadecimal escapes (%nn).</span></span>  
  
    -   <span data-ttu-id="1c9ac-124">유니코드 이스케이프(%nnn)</span><span class="sxs-lookup"><span data-stu-id="1c9ac-124">Unicode escapes (%nnn).</span></span>  
  
    -   <span data-ttu-id="1c9ac-125">과도하게 긴 UTF-8 이스케이프(%nn%nn)</span><span class="sxs-lookup"><span data-stu-id="1c9ac-125">Overlong UTF-8 escapes (%nn%nn).</span></span>  
  
    -   <span data-ttu-id="1c9ac-126">배정밀도 이스케이프(%nn은 %mmnn이 됨. 여기에서 %mm은 '%'의 이스케이프)</span><span class="sxs-lookup"><span data-stu-id="1c9ac-126">Double escapes (%nn becomes %mmnn, where %mm is the escape for '%').</span></span>  
  
-   <span data-ttu-id="1c9ac-127">둘 이상의 정규 형식이 있을 수 있는 사용자 이름에 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="1c9ac-127">Be wary of user names that might have more than one canonical format.</span></span> <span data-ttu-id="1c9ac-128">예를 들어, 종종 MYDOMAIN\\*username* 형식 또는 *username*@mydomain.example.com 형식 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9ac-128">For example, you can often use either the MYDOMAIN\\*username* form or the *username*@mydomain.example.com form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c9ac-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c9ac-129">See Also</span></span>  
 [<span data-ttu-id="1c9ac-130">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="1c9ac-130">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
