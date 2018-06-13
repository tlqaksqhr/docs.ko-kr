---
title: '#ExternalSource 지시문'
ms.date: 07/20/2015
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
ms.openlocfilehash: 146ab41d74b45acc4063e2463baca26c7caa4652
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586593"
---
# <a name="externalsource-directive"></a><span data-ttu-id="b1d57-102">#ExternalSource 지시문</span><span class="sxs-lookup"><span data-stu-id="b1d57-102">#ExternalSource Directive</span></span>
<span data-ttu-id="b1d57-103">소스 코드의 특정 줄과 소스 외부에 있는 텍스트 간의 매핑을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1d57-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1d57-104">구문</span><span class="sxs-lookup"><span data-stu-id="b1d57-104">Syntax</span></span>  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="b1d57-105">요소</span><span class="sxs-lookup"><span data-stu-id="b1d57-105">Parts</span></span>  
 `StringLiteral`  
 <span data-ttu-id="b1d57-106">외부 원본에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b1d57-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="b1d57-107">외부 소스의 첫 번째 줄의 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b1d57-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="b1d57-108">외부 소스에서 오류가 발생 하는 선입니다.</span><span class="sxs-lookup"><span data-stu-id="b1d57-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="b1d57-109">`#ExternalSource` 블록을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d57-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1d57-110">설명</span><span class="sxs-lookup"><span data-stu-id="b1d57-110">Remarks</span></span>  
 <span data-ttu-id="b1d57-111">이 지시문은 컴파일러와 디버거에 의해서만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d57-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="b1d57-112">소스 파일을 소스 파일에 코드의 특정 줄과.aspx 파일과 같이 소스 외부에 텍스트 간의 매핑을 나타내는 외부 원본 지시문이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d57-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="b1d57-113">지정된 된 소스 코드에서 컴파일하는 동안 오류가 발생 하면 외부 원본에서 오는 것으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d57-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="b1d57-114">외부 소스 지시문 컴파일에 영향을 주 및 중첩 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d57-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="b1d57-115">응용 프로그램에서 내부 사용에 대 한 것은.</span><span class="sxs-lookup"><span data-stu-id="b1d57-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d57-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1d57-116">See Also</span></span>  
 [<span data-ttu-id="b1d57-117">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="b1d57-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
