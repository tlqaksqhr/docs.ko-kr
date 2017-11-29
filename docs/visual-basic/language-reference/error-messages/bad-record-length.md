---
title: "레코드 길이가 잘못되었습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 747d62cb41ef841b4486e0c7108c37a86929683e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="bad-record-length"></a><span data-ttu-id="41e84-102">레코드 길이가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41e84-102">Bad record length</span></span>
<span data-ttu-id="41e84-103">이 오류의 가능한 원인:</span><span class="sxs-lookup"><span data-stu-id="41e84-103">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="41e84-104">에 지정 된 레코드 변수의 길이 `FileGet`, `FileGetObject`, `FilePut` 또는 `FilePutObject` 해당에 지정 된 길이에서 다른 문을 `FileOpen` 문.</span><span class="sxs-lookup"><span data-stu-id="41e84-104">The length of a record variable specified in a `FileGet`, `FileGetObject`, `FilePut` or `FilePutObject` statement differs from the length specified in the corresponding `FileOpen` statement.</span></span>  
  
-   <span data-ttu-id="41e84-105">변수는 `FilePut` 또는 `FilePutObject` 문이 하거나 다양 한 길이의 문자열을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="41e84-105">The variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string.</span></span>  
  
-   <span data-ttu-id="41e84-106">변수는 `FilePut` 또는 `FilePutObject` 되거나 포함 하는 `Variant` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="41e84-106">The variable in a `FilePut` or `FilePutObject` is or includes a `Variant` type.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="41e84-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="41e84-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="41e84-108">인지 확인 레코드 변수의 형식을 정의 하는 사용자 정의 형식에서 고정 길이 변수의 크기의 합계와 동일한 값에 명시 된 대로 `FileOpen` 문의 `Len` 절.</span><span class="sxs-lookup"><span data-stu-id="41e84-108">Make sure the sum of the sizes of fixed-length variables in the user-defined type defining the record variable's type is the same as the value stated in the `FileOpen` statement's `Len` clause.</span></span>  
  
2.  <span data-ttu-id="41e84-109">경우에 변수가 `FilePut` 또는 `FilePutObject` , 다양 한 길이의 문자열 길이 최소 2 자 레코드에 지정 된 길이 보다 짧은 반드시 문이 하거나 다양 한 길이의 문자열을 포함는 `Len` 절은 `FileOpen` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="41e84-109">If the variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string, make sure the variable-length string is at least 2 characters shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
3.  <span data-ttu-id="41e84-110">하는 경우의 변수는 `FilePut` 또는 `FilePutObject` 되거나 포함 하는 `Variant` 가변 길이 문자열에 지정 된 레코드 길이 보다 짧은 4 바이트 이상 인지 확인는 `Len` 절은 `FileOpen` 문.</span><span class="sxs-lookup"><span data-stu-id="41e84-110">If the variable in a `FilePut` or `FilePutObject` is or includes a `Variant` make sure the variable-length string is at least 4 bytes shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e84-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41e84-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
