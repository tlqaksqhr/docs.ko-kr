---
title: "방법: Visual Basic에서 XML 문서 만들기 | Microsoft 문서"
ms.custom: 
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
- XML comments
- XML documentation, creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
caps.latest.revision: 17
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
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 3171877f4fa1913b5535d71d671cea97b5a22850
ms.contentlocale: ko-kr
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="f5e6f-102">방법: Visual Basic에서 XML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="f5e6f-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="f5e6f-103">이 예제에서는 XML 문서 주석 코드를 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5e6f-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="f5e6f-104">형식 또는 멤버에 대 한 XML 문서를 만들려면</span><span class="sxs-lookup"><span data-stu-id="f5e6f-104">To create XML documentation for a type or member</span></span>  
  
1.  <span data-ttu-id="f5e6f-105">에 **코드 편집기**, 설명서를 만들려는 형식 또는 멤버 위의 줄에 커서를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="f5e6f-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2.  <span data-ttu-id="f5e6f-106">형식 `'''` (세 단일 인용 부호 제외).</span><span class="sxs-lookup"><span data-stu-id="f5e6f-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="f5e6f-107">형식 또는 멤버에 대 한 XML 기초가에 추가 되는 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e6f-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="f5e6f-108">적절 한 태그 사이 설명 정보를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e6f-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f5e6f-109">XML 문서 블록 내에서 줄을 추가 하는 경우에 각 줄으로 시작 해야 `'''`합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e6f-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4.  <span data-ttu-id="f5e6f-110">새 XML 문서 주석이 있는 형식 또는 멤버를 사용 하는 추가 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e6f-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="f5e6f-111">텍스트를 표시 하는 IntelliSense는 \<요약 > 형식 또는 멤버에 대 한 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="f5e6f-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5.  <span data-ttu-id="f5e6f-112">문서 주석을 포함 하는 XML 파일을 생성 하는 코드를 컴파일하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5e6f-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="f5e6f-113">자세한 내용은 참조 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e6f-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5e6f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5e6f-114">See Also</span></span>  
 <span data-ttu-id="f5e6f-115">[XML 사용 하 여 코드 문서화](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span><span class="sxs-lookup"><span data-stu-id="f5e6f-115">[Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span></span>  
<span data-ttu-id="f5e6f-116"> [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) </span><span class="sxs-lookup"><span data-stu-id="f5e6f-116"> [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) </span></span>  
<span data-ttu-id="f5e6f-117"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)</span><span class="sxs-lookup"><span data-stu-id="f5e6f-117"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)</span></span>
