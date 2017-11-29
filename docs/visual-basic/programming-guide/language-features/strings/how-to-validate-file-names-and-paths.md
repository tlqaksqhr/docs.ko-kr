---
title: "방법: Visual Basic에서 파일 이름 및 경로 확인"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9c50d09dd7160992ffd95ececeff623a8aa93d2d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="e1778-102">방법: Visual Basic에서 파일 이름 및 경로 확인</span><span class="sxs-lookup"><span data-stu-id="e1778-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="e1778-103">이 예제에서는 반환 된 `Boolean` 문자열이 파일 이름 또는 경로 나타내는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e1778-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="e1778-104">유효성 검사 이름 파일 시스템에서 허용 되지 않는 문자를 포함 하는 경우를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1778-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1778-105">예제</span><span class="sxs-lookup"><span data-stu-id="e1778-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 <span data-ttu-id="e1778-106">이 예제에서는 이름이 위치가 잘못 되었는지 콜론으로 구분 하거나 이름이 없는 디렉터리 또는 이름의 길이 시스템 정의 최대 길이 초과 하는 경우를 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1778-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="e1778-107">또한 확인 하지 않습니다 응용 프로그램은 지정 된 이름의 파일 시스템 리소스에 액세스 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="e1778-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1778-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1778-108">See Also</span></span>  
 <xref:System.IO.Path.GetInvalidPathChars%2A>  
 [<span data-ttu-id="e1778-109">Visual Basic의 문자열 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="e1778-109">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
