---
title: Assembly(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef4434f0bc520abfc621567fc68e0b8bcfd6e381
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="12dd9-102">Assembly(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12dd9-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="12dd9-103">소스 파일의 시작 부분에 있는 특성이 전체 어셈블리에 적용 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="12dd9-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12dd9-104">설명</span><span class="sxs-lookup"><span data-stu-id="12dd9-104">Remarks</span></span>  
 <span data-ttu-id="12dd9-105">다 수의 특성이 클래스나 속성 같은 개별 프로그래밍 요소에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12dd9-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="12dd9-106">꺾쇠 괄호 안에 특성 블록을 연결 하 여 특성을 적용 (`< >`), 선언문에 직접 합니다.</span><span class="sxs-lookup"><span data-stu-id="12dd9-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="12dd9-107">특성에 다음 요소 뿐 아니라 전체 어셈블리에 관련 된 경우 소스 파일의 시작 부분에 특성 블록을 저장 한 특성으로 식별 한는 `Assembly` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="12dd9-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="12dd9-108">사용 하면 현재 어셈블리 모듈에 해당 되는 경우는 [모듈](../../../visual-basic/language-reference/modifiers/module-keyword.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="12dd9-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="12dd9-109">적용할 수 있습니다도 특성 AssemblyInfo.vb 파일에 있는 어셈블리를 주 소스 코드 파일에 특성 블록을 사용할 필요가 없습니다는 경우.</span><span class="sxs-lookup"><span data-stu-id="12dd9-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12dd9-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12dd9-110">See Also</span></span>  
 [<span data-ttu-id="12dd9-111">모듈 \<키워드></span><span class="sxs-lookup"><span data-stu-id="12dd9-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [<span data-ttu-id="12dd9-112">특성 개요</span><span class="sxs-lookup"><span data-stu-id="12dd9-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

