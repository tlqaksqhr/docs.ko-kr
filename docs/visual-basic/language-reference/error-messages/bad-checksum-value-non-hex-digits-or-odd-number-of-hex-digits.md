---
title: "잘못 된 체크섬 값, 비&16; 진수 또는&16; 진수의 홀수 번호 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42033
- vbc42033
dev_langs:
- VB
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
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
ms.openlocfilehash: 70a8fc5e0200c15858ad1288e12b2aeb1e5303d8
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a><span data-ttu-id="e21c9-102">체크섬 값이 잘못되었습니다.&16;진수가 아니거나&16;진수 값이 홀수입니다.</span><span class="sxs-lookup"><span data-stu-id="e21c9-102">Bad checksum value, non hex digits or odd number of hex digits</span></span>
<span data-ttu-id="e21c9-103">체크섬 값의&16;진수가 잘못되었거나 자릿수가 홀수입니다.</span><span class="sxs-lookup"><span data-stu-id="e21c9-103">A checksum value contains invalid hexadecimal digits or has an odd number of digits.</span></span>  
  
 <span data-ttu-id="e21c9-104">ASP.NET은 Visual Basic 소스 파일(확장명 .vb)을 생성할 때 체크섬을 계산하여 `#externalchecksum`으로 식별되는 숨겨진 소스 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e21c9-104">When ASP.NET generates a Visual Basic source file (extension .vb), it calculates a checksum and places it in a hidden source file identified by `#externalchecksum`.</span></span> <span data-ttu-id="e21c9-105">.vb 파일을 생성하는 사용자도 이 작업을 수행할 수 있지만 해당 프로세스는 내부용으로 유지하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e21c9-105">It is possible for a user generating a .vb file to do this also, but this process is best left to internal use.</span></span>  
  
 <span data-ttu-id="e21c9-106">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="e21c9-106">By default, this message is a warning.</span></span> <span data-ttu-id="e21c9-107">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e21c9-107">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e21c9-108">**오류 ID:** BC42033</span><span class="sxs-lookup"><span data-stu-id="e21c9-108">**Error ID:** BC42033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e21c9-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="e21c9-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="e21c9-110">ASP.NET에서 Visual Basic 소스 파일을 생성하는 경우 프로젝트 빌드를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e21c9-110">If ASP.NET is generating the Visual Basic source file, restart the project build.</span></span>  
  
2.  <span data-ttu-id="e21c9-111">빌드를 다시 시작한 후에도 이 경고가 계속 발생하면 ASP.NET을 다시 설치하고 빌드를 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="e21c9-111">If this warning persists after restarting, reinstall ASP.NET and try the build again.</span></span>  
  
3.  <span data-ttu-id="e21c9-112">그래도 경고가 계속 발생하거나 ASP.NET을 사용하고 있지 않으면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e21c9-112">If the warning still persists, or if you are not using ASP.NET, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e21c9-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e21c9-113">See Also</span></span>  
 <span data-ttu-id="e21c9-114">[ASP.NET 개요](https://msdn.microsoft.com/library/4w3ex9c2.aspx) </span><span class="sxs-lookup"><span data-stu-id="e21c9-114">[ASP.NET Overview](https://msdn.microsoft.com/library/4w3ex9c2.aspx) </span></span>  
<span data-ttu-id="e21c9-115"> [의견 보내기](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="e21c9-115"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>
