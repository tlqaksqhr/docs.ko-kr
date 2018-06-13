---
title: Assembly(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
ms.openlocfilehash: 7ee6cddefd5955ee76510ffeb23335f05460657b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595292"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="9748d-102">Assembly(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9748d-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="9748d-103">소스 파일의 시작 부분에 있는 특성이 전체 어셈블리에 적용 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9748d-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9748d-104">설명</span><span class="sxs-lookup"><span data-stu-id="9748d-104">Remarks</span></span>  
 <span data-ttu-id="9748d-105">다 수의 특성이 클래스나 속성 같은 개별 프로그래밍 요소에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9748d-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="9748d-106">꺾쇠 괄호 안에 특성 블록을 연결 하 여 특성을 적용 (`< >`), 선언문에 직접 합니다.</span><span class="sxs-lookup"><span data-stu-id="9748d-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="9748d-107">특성에 다음 요소 뿐 아니라 전체 어셈블리에 관련 된 경우 소스 파일의 시작 부분에 특성 블록을 저장 한 특성으로 식별 한는 `Assembly` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="9748d-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="9748d-108">사용 하면 현재 어셈블리 모듈에 해당 되는 경우는 [모듈](../../../visual-basic/language-reference/modifiers/module-keyword.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="9748d-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="9748d-109">적용할 수 있습니다도 특성 AssemblyInfo.vb 파일에 있는 어셈블리를 주 소스 코드 파일에 특성 블록을 사용할 필요가 없습니다는 경우.</span><span class="sxs-lookup"><span data-stu-id="9748d-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9748d-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9748d-110">See Also</span></span>  
 [<span data-ttu-id="9748d-111">모듈 \<키워드></span><span class="sxs-lookup"><span data-stu-id="9748d-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [<span data-ttu-id="9748d-112">특성 개요</span><span class="sxs-lookup"><span data-stu-id="9748d-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

