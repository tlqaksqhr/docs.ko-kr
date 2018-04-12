---
title: '&#39; 줄 &#39; 문은 더 이상 지원 (Visual Basic 컴파일러 오류)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d2db5dc786749360dfcf6789f12b5659d5713fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="39line39-statements-are-no-longer-supported-visual-basic-compiler-error"></a><span data-ttu-id="7cb03-102">&#39; 줄 &#39; 문은 더 이상 지원 (Visual Basic 컴파일러 오류)</span><span class="sxs-lookup"><span data-stu-id="7cb03-102">&#39;Line&#39; statements are no longer supported (Visual Basic Compiler Error)</span></span>
<span data-ttu-id="7cb03-103">줄으로 된 문이 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb03-103">Line statements are no longer supported.</span></span> <span data-ttu-id="7cb03-104">파일 I/O 기능은 `Microsoft.VisualBasic.FileSystem.LineInput` 그래픽 기능으로 서 제공 `System.Drawing.Graphics.DrawLine`합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb03-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>  
  
 <span data-ttu-id="7cb03-105">**오류 ID:** BC30830</span><span class="sxs-lookup"><span data-stu-id="7cb03-105">**Error ID:** BC30830</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7cb03-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="7cb03-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="7cb03-107">파일 액세스를 수행 하는 경우 사용 하 여 `Microsoft.VisualBasic.FileSystem.LineInput`합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb03-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>  
  
2.  <span data-ttu-id="7cb03-108">그래픽을 수행 하는 경우 사용 하 여 `System.Drawing.Graphics.Drawline`합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb03-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cb03-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7cb03-109">See Also</span></span>  
 <xref:System.IO>  
 <xref:System.Drawing>  
 [<span data-ttu-id="7cb03-110">Visual Basic을 사용한 파일 액세스</span><span class="sxs-lookup"><span data-stu-id="7cb03-110">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
