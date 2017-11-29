---
title: "DLL을 로드하는 동안 오류가 발생했습니다(Visual Basic)."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cc557dcc6709178b6519adb56f31debcbd1d1c39
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="f1571-102">DLL을 로드하는 동안 오류가 발생했습니다(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="f1571-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="f1571-103">동적 연결 라이브러리 (DLL)는에 지정 된 라이브러리는 `Lib` 절은 `Declare` 문.</span><span class="sxs-lookup"><span data-stu-id="f1571-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="f1571-104">이 오류에 대 한 가능한 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f1571-104">Possible causes for this error include:</span></span>  
  
-   <span data-ttu-id="f1571-105">파일이 DLL로 실행할 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f1571-105">The file is not DLL executable.</span></span>  
  
-   <span data-ttu-id="f1571-106">Microsoft Windows DLL 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1571-106">The file is not a Microsoft Windows DLL.</span></span>  
  
-   <span data-ttu-id="f1571-107">DLL에는 존재 하지 않는 다른 DLL 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1571-107">The DLL references another DLL that is not present.</span></span>  
  
-   <span data-ttu-id="f1571-108">DLL 또는 참조 DLL 경로에 지정 하는 디렉터리에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1571-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f1571-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f1571-109">To correct this error</span></span>  
  
-   <span data-ttu-id="f1571-110">해당 파일을 소스 텍스트 파일 및 따라서 경우에 컴파일된을 DLL 실행 가능한 폼에 연결 될 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1571-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
-   <span data-ttu-id="f1571-111">Microsoft Windows DLL 파일이 없는 경우 해당 하는 Microsoft Windows를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f1571-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
-   <span data-ttu-id="f1571-112">DLL 참조는 존재 하지 않는 다른 DLL, 참조 DLL 받으며 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1571-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
-   <span data-ttu-id="f1571-113">DLL 또는 참조 된 DLL의 경로 지정 된 디렉터리에 없으면 DLL 참조 디렉터리로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1571-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1571-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1571-114">See Also</span></span>  
 [<span data-ttu-id="f1571-115">Declare 문</span><span class="sxs-lookup"><span data-stu-id="f1571-115">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
