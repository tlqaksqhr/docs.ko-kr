---
title: '방법: Visual Basic에서 XML 문서 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 7fb56da8a28367a6dcd5e28f208b4519510d7d95
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39243881"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="c39fb-102">방법: Visual Basic에서 XML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="c39fb-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="c39fb-103">이 예제에서는 XML 문서 주석 코드를 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c39fb-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="c39fb-104">형식 또는 멤버에 대 한 XML 문서를 만들려면</span><span class="sxs-lookup"><span data-stu-id="c39fb-104">To create XML documentation for a type or member</span></span>  
  
1.  <span data-ttu-id="c39fb-105">에 **코드 편집기**, 문서를 만들려면 형식 또는 멤버는 위의 줄에 커서를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="c39fb-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2.  <span data-ttu-id="c39fb-106">형식 `'''` (세 개의 작은따옴표).</span><span class="sxs-lookup"><span data-stu-id="c39fb-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="c39fb-107">형식 또는 멤버는 XML 구조에 추가 되는 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="c39fb-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="c39fb-108">적절 한 태그 사이 설명 정보를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c39fb-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c39fb-109">각 줄으로 시작 해야 XML 문서 블록에 추가 줄을 추가 하는 경우 `'''`합니다.</span><span class="sxs-lookup"><span data-stu-id="c39fb-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4.  <span data-ttu-id="c39fb-110">새 XML 문서 주석이 포함 된 형식 또는 멤버를 사용 하는 추가 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c39fb-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="c39fb-111">텍스트를 표시 하는 IntelliSense를 \<요약 > 형식 또는 멤버에 대 한 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="c39fb-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5.  <span data-ttu-id="c39fb-112">설명서 주석이 들어 있는 XML 파일을 생성 하는 코드를 컴파일하십시오.</span><span class="sxs-lookup"><span data-stu-id="c39fb-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="c39fb-113">자세한 내용은 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c39fb-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c39fb-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c39fb-114">See Also</span></span>  
 [<span data-ttu-id="c39fb-115">코드를 XML로 문서화</span><span class="sxs-lookup"><span data-stu-id="c39fb-115">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="c39fb-116">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="c39fb-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
 [<span data-ttu-id="c39fb-117">/doc</span><span class="sxs-lookup"><span data-stu-id="c39fb-117">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
