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
ms.openlocfilehash: 76e4082710a6786ec5e743ce606e849637c26512
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a><span data-ttu-id="0005e-102">이벤트 로그에 대해 잘못된 이름을 지정했습니다.</span><span class="sxs-lookup"><span data-stu-id="0005e-102">An invalid name was specified for the event log</span></span>
<span data-ttu-id="0005e-103">이벤트 로그에 대해 잘못된 이름을 지정했습니다.</span><span class="sxs-lookup"><span data-stu-id="0005e-103">An invalid name was specified for the event log.</span></span> <span data-ttu-id="0005e-104">일반적으로 이름, 빈 파일 이름 또는 너무 긴 파일 이름에 잘못된 문자가 포함되어 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0005e-104">Usually this is a result of invalid characters in the name, a blank file name, or a file name that is too long.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0005e-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="0005e-105">To correct this error</span></span>  
  
-   <span data-ttu-id="0005e-106">지정된 이름이 8자보다 긴 경우 다른 이벤트 로그 이름과 충돌하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0005e-106">If the specified name is more than eight characters, make sure there is no conflict with the names of other event logs.</span></span> <span data-ttu-id="0005e-107">이름이 고유한지 확인할 때 처음 8자만 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="0005e-107">Only the first eight characters are evaluated when determining if the name is unique.</span></span>  
  
-   <span data-ttu-id="0005e-108">경로를 제공하는 경우 제대로 구문 분석되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0005e-108">If supplying a path, make sure it is parsed correctly.</span></span>  
  
-   <span data-ttu-id="0005e-109">이름에 잘못된 문자가 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0005e-109">Check that there are no invalid characters in the name.</span></span> <span data-ttu-id="0005e-110">`<`, `>`, `:`, `"`, `/`, `\`및 `|`는 파일 이름에 사용할 수 없는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="0005e-110">Characters that cannot be used in a file name include `<`, `>`, `:`, `"`, `/`, `\`, and `|`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0005e-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0005e-111">See Also</span></span>  
 [<span data-ttu-id="0005e-112">방법: 파일 경로의 구문 분석</span><span class="sxs-lookup"><span data-stu-id="0005e-112">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)  
 [<span data-ttu-id="0005e-113">방법: 파일 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="0005e-113">How to: Rename a File</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)  
 
