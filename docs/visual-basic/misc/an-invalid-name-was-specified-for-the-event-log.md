---
title: "이벤트 로그에 대해 잘못된 이름을 지정했습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fc5a2e93541063a129efaa0ce08fc19a98372126
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a><span data-ttu-id="b7bf0-102">이벤트 로그에 대해 잘못된 이름을 지정했습니다.</span><span class="sxs-lookup"><span data-stu-id="b7bf0-102">An invalid name was specified for the event log</span></span>
<span data-ttu-id="b7bf0-103">이벤트 로그에 대해 잘못된 이름을 지정했습니다.</span><span class="sxs-lookup"><span data-stu-id="b7bf0-103">An invalid name was specified for the event log.</span></span> <span data-ttu-id="b7bf0-104">일반적으로 이름, 빈 파일 이름 또는 너무 긴 파일 이름에 잘못된 문자가 포함되어 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b7bf0-104">Usually this is a result of invalid characters in the name, a blank file name, or a file name that is too long.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b7bf0-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="b7bf0-105">To correct this error</span></span>  
  
-   <span data-ttu-id="b7bf0-106">지정된 이름이 8자보다 긴 경우 다른 이벤트 로그 이름과 충돌하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7bf0-106">If the specified name is more than eight characters, make sure there is no conflict with the names of other event logs.</span></span> <span data-ttu-id="b7bf0-107">이름이 고유한지 확인할 때 처음 8자만 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="b7bf0-107">Only the first eight characters are evaluated when determining if the name is unique.</span></span>  
  
-   <span data-ttu-id="b7bf0-108">경로를 제공하는 경우 제대로 구문 분석되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7bf0-108">If supplying a path, make sure it is parsed correctly.</span></span>  
  
-   <span data-ttu-id="b7bf0-109">이름에 잘못된 문자가 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b7bf0-109">Check that there are no invalid characters in the name.</span></span> <span data-ttu-id="b7bf0-110">`<`, `>`, `:`, `"`, `/`, `\`및 `|`는 파일 이름에 사용할 수 없는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="b7bf0-110">Characters that cannot be used in a file name include `<`, `>`, `:`, `"`, `/`, `\`, and `|`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7bf0-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7bf0-111">See Also</span></span>  
 [<span data-ttu-id="b7bf0-112">방법: 파일 경로의 구문 분석</span><span class="sxs-lookup"><span data-stu-id="b7bf0-112">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)  
 [<span data-ttu-id="b7bf0-113">방법: 파일 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="b7bf0-113">How to: Rename a File</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)  
 [<span data-ttu-id="b7bf0-114">방법: 만들기 및 사용자 지정 이벤트 로그 제거</span><span class="sxs-lookup"><span data-stu-id="b7bf0-114">How to: Create and Remove Custom Event Logs</span></span>](http://msdn.microsoft.com/en-us/af9b7da0-80c7-46ac-b7f7-897063ddd503)
