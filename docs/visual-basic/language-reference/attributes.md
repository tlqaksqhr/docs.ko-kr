---
title: "특성 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- attributes [Visual Basic]
ms.assetid: 5deb2b8a-1afd-4dbd-8ee8-f093d74ad0eb
caps.latest.revision: 12
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
ms.openlocfilehash: d12b9e587d7b57998edff1559d24d0e7d4bda6ce
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="attributes-visual-basic"></a><span data-ttu-id="a03a6-102">특성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a03a6-102">Attributes (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="a03a6-103">개체가 비관리 코드와 상호 작용을 허용 하는 몇 가지 특성 및 모듈 멤버에는 모듈 이름 없이 액세스할 수 있도록 하나의 특성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03a6-103"> provides several attributes that allow objects interoperate with unmanaged code, and one attribute that enables module members to be accessed without the module name.</span></span> <span data-ttu-id="a03a6-104">다음 표에서 사용 되는 특성 [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="a03a6-104">The following table lists the attributes used by [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="a03a6-105"><xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute></span><span class="sxs-lookup"><span data-stu-id="a03a6-105"><xref:Microsoft.VisualBasic.ComClassAttribute></span></span>|<span data-ttu-id="a03a6-106">클래스를 COM 개체로 노출 될 수 있는 메타 데이터를 추가 하도록 컴파일러에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03a6-106">Instructs the compiler to add metadata that allows a class to be exposed as a COM object.</span></span>|  
|<span data-ttu-id="a03a6-107"><xref:Microsoft.VisualBasic.HideModuleNameAttribute></xref:Microsoft.VisualBasic.HideModuleNameAttribute></span><span class="sxs-lookup"><span data-stu-id="a03a6-107"><xref:Microsoft.VisualBasic.HideModuleNameAttribute></span></span>|<span data-ttu-id="a03a6-108">모듈 멤버에는 모듈에 대 한 필요한 한정만을 사용 하 여 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03a6-108">Allows the module members to be accessed using only the qualification needed for the module.</span></span>|  
|<span data-ttu-id="a03a6-109"><xref:Microsoft.VisualBasic.VBFixedArrayAttribute></xref:Microsoft.VisualBasic.VBFixedArrayAttribute></span><span class="sxs-lookup"><span data-stu-id="a03a6-109"><xref:Microsoft.VisualBasic.VBFixedArrayAttribute></span></span>|<span data-ttu-id="a03a6-110">구조 또는 비 로컬 변수에서 배열을 고정 길이 배열을로 처리 되어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a03a6-110">Indicates that an array in a structure or non-local variable should be treated as a fixed-length array.</span></span>|  
|<span data-ttu-id="a03a6-111"><xref:Microsoft.VisualBasic.VBFixedStringAttribute></xref:Microsoft.VisualBasic.VBFixedStringAttribute></span><span class="sxs-lookup"><span data-stu-id="a03a6-111"><xref:Microsoft.VisualBasic.VBFixedStringAttribute></span></span>|<span data-ttu-id="a03a6-112">문자열 길이 수정 된 경우 처럼 처리 되어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a03a6-112">Indicates that a string should be treated as if it were fixed length.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a03a6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a03a6-113">See Also</span></span>  
 [<span data-ttu-id="a03a6-114">특성 개요</span><span class="sxs-lookup"><span data-stu-id="a03a6-114">Attributes overview</span></span>](../../visual-basic/programming-guide/concepts/attributes/index.md)

