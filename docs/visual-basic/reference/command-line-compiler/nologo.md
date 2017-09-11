---
title: "/nologo (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners, suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
caps.latest.revision: 16
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
ms.openlocfilehash: fe03c36f46717248269c9aaec13b40569161b0e0
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="nologo-visual-basic"></a><span data-ttu-id="1a275-102">/nologo(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a275-102">/nologo (Visual Basic)</span></span>
<span data-ttu-id="1a275-103">컴파일하는 동안 저작권 배너 및 정보 메시지 표시를 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a275-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a275-104">구문</span><span class="sxs-lookup"><span data-stu-id="1a275-104">Syntax</span></span>  
  
```  
/nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="1a275-105">설명</span><span class="sxs-lookup"><span data-stu-id="1a275-105">Remarks</span></span>  
 <span data-ttu-id="1a275-106">지정 하는 경우 `/nologo`, 컴파일러 저작권 배너를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a275-106">If you specify `/nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="1a275-107">기본적으로 `/nologo`은 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a275-107">By default, `/nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a275-108">`/nologo` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a275-108">The `/nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a275-109">예제</span><span class="sxs-lookup"><span data-stu-id="1a275-109">Example</span></span>  
 <span data-ttu-id="1a275-110">다음 코드에서는 `T2.vb` 를 저작권 배너를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a275-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```  
vbc /nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a275-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a275-111">See Also</span></span>  
 <span data-ttu-id="1a275-112">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="1a275-112">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="1a275-113"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="1a275-113"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
