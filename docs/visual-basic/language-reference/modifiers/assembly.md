---
title: "Assembly (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
dev_langs:
- VB
helpviewer_keywords:
- Assembly modifier
- Assembly keyword
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: 15
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
ms.openlocfilehash: b83102c24c80b7ee6ec4c0ffc4a446e26b7811cf
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="assembly-visual-basic"></a><span data-ttu-id="5b0ea-102">Assembly(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b0ea-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="5b0ea-103">소스 파일의 시작 부분에 있는 특성이 전체 어셈블리에 적용 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b0ea-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b0ea-104">주의</span><span class="sxs-lookup"><span data-stu-id="5b0ea-104">Remarks</span></span>  
 <span data-ttu-id="5b0ea-105">많은 특성 클래스 또는 속성과 같은 개별 프로그래밍 요소와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b0ea-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="5b0ea-106">꺾쇠 괄호 안에 특성 블록을 연결 하 여 특성을 적용 (`< >`), 선언문에 직접.</span><span class="sxs-lookup"><span data-stu-id="5b0ea-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="5b0ea-107">소스 파일의 시작 부분에는 특성 블록을 배치 하 고 있는 특성으로 식별 특성에 다음 요소 뿐 아니라 전체 어셈블리에 관련 된 경우는 `Assembly` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="5b0ea-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="5b0ea-108">현재 어셈블리 모듈에 적용 되는 경우 사용 된 [모듈](../../../visual-basic/language-reference/modifiers/module-keyword.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="5b0ea-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="5b0ea-109">적용할 수 있습니다도 특성 AssemblyInfo.vb 파일에 있는 어셈블리를 주 소스 코드 파일에 특성 블록을 사용할 필요가 없습니다 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="5b0ea-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b0ea-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b0ea-110">See Also</span></span>  
 <span data-ttu-id="5b0ea-111">[모듈 \<키워드 >](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span><span class="sxs-lookup"><span data-stu-id="5b0ea-111">[Module \<keyword>](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span></span>  
<span data-ttu-id="5b0ea-112"> [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)</span><span class="sxs-lookup"><span data-stu-id="5b0ea-112"> [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md)</span></span>


