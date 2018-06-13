---
title: Ansi(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: c7037acac58de56a396bd89f595ef897743ff4e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595081"
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="717f6-102">Ansi(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="717f6-102">Ansi (Visual Basic)</span></span>
<span data-ttu-id="717f6-103">Visual Basic 선언 되는 외부 프로시저의 이름에 관계 없이 American National Standards Institute (ANSI) 값으로 모든 문자열을 마샬링하고 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="717f6-103">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="717f6-104">프로젝트 외부에 정의 된 프로시저를 호출 하는 경우 Visual Basic 컴파일러 올바르게 프로시저를 호출 하는 데 필요한 정보에 액세스할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="717f6-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="717f6-105">문자열 문자 집합 및이 정보에는 프로시저의 위치, 식별 되는 방법, 호출 시퀀스 및 반환 형식으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="717f6-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="717f6-106">[선언 문의](../../../visual-basic/language-reference/statements/declare-statement.md) 외부 프로시저에 대 한 참조를 만들고이 필요한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="717f6-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="717f6-107">`charsetmodifier` 부분은 `Declare` 문은 외부 프로시저를 호출 하는 동안 문자열을 마샬링 한 문자 집합 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="717f6-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="717f6-108">Visual Basic에서 외부 프로시저 이름에 대 한 외부 파일을 검색 하는 방법도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="717f6-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="717f6-109">`Ansi` 한정자는 Visual Basic에서 모든 문자열을 ANSI 값으로 마샬링하고 이름을 검색 하는 동안 수정 하지 않고 프로시저를 조회 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="717f6-109">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="717f6-110">문자 집합 자가 지정 된 경우 `Ansi` 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="717f6-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="717f6-111">설명</span><span class="sxs-lookup"><span data-stu-id="717f6-111">Remarks</span></span>  
 <span data-ttu-id="717f6-112">`Ansi` 한정자는이 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="717f6-112">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="717f6-113">Declare 문</span><span class="sxs-lookup"><span data-stu-id="717f6-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="717f6-114">스마트 장치 개발자 노트</span><span class="sxs-lookup"><span data-stu-id="717f6-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="717f6-115">이 키워드는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="717f6-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="717f6-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="717f6-116">See Also</span></span>  
 [<span data-ttu-id="717f6-117">자동</span><span class="sxs-lookup"><span data-stu-id="717f6-117">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)  
 [<span data-ttu-id="717f6-118">유니코드</span><span class="sxs-lookup"><span data-stu-id="717f6-118">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [<span data-ttu-id="717f6-119">키워드</span><span class="sxs-lookup"><span data-stu-id="717f6-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
