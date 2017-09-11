---
title: "XML 파일 (Visual Basic) 처리 | Microsoft 문서"
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
- XML comments, parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
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
ms.openlocfilehash: cf15cf59413e0e019086dd1a79951ccb212f037b
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="processing-the-xml-file-visual-basic"></a><span data-ttu-id="9bd2b-102">XML 파일 처리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bd2b-102">Processing the XML File (Visual Basic)</span></span>
<span data-ttu-id="9bd2b-103">컴파일러는 문서를 생성 하는 태그가 지정 되는 코드의 각 구문에는 ID 문자열을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="9bd2b-104">(코드를 태그 하는 방법에 대 한 자세한 내용은 참조 [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) ID 문자열 구문을 고유 하 게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-104">(For information on how to tag your code, see [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="9bd2b-105">해당 식별 하는 XML 파일을 처리 하는 프로그램 ID 문자열을 사용 하 여 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 메타 데이터/리플렉션 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-105">Programs that process the XML file can use the ID string to identify the corresponding [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] metadata/reflection item.</span></span>  
  
 <span data-ttu-id="9bd2b-106">XML 파일의 코드, 계층적 나타내지는 않습니다. 각 요소에 대해 생성된 된 ID로 플랫 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-106">The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.</span></span>  
  
 <span data-ttu-id="9bd2b-107">ID 문자열을 생성 하는 경우 컴파일러는 다음 규칙을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-107">The compiler observes the following rules when it generates the ID strings:</span></span>  
  
-   <span data-ttu-id="9bd2b-108">공백이 없습니다 문자열에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-108">No white space is placed in the string.</span></span>  
  
-   <span data-ttu-id="9bd2b-109">ID 문자열의 첫 번째 부분 뒤에 콜론을 단일 문자로 식별 되 고 멤버의 종류를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-109">The first part of the ID string identifies the kind of member being identified, with a single character followed by a colon.</span></span> <span data-ttu-id="9bd2b-110">다음과 같은 멤버 형식은 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-110">The following member types are used.</span></span>  
  
|<span data-ttu-id="9bd2b-111">문자</span><span class="sxs-lookup"><span data-stu-id="9bd2b-111">Character</span></span>|<span data-ttu-id="9bd2b-112">설명</span><span class="sxs-lookup"><span data-stu-id="9bd2b-112">Description</span></span>|  
|---|---|  
|<span data-ttu-id="9bd2b-113">N</span><span class="sxs-lookup"><span data-stu-id="9bd2b-113">N</span></span>|<span data-ttu-id="9bd2b-114">namespace</span><span class="sxs-lookup"><span data-stu-id="9bd2b-114">namespace</span></span><br /><br /> <span data-ttu-id="9bd2b-115">네임 스페이스 문서 주석을 추가할 수 없지만, 스토리에 대 한 CREF 참조를 만들 수 있습니다 지원 되는 경우.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-115">You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.</span></span>|  
|<span data-ttu-id="9bd2b-116">T</span><span class="sxs-lookup"><span data-stu-id="9bd2b-116">T</span></span>|<span data-ttu-id="9bd2b-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`,`Delegate`</span><span class="sxs-lookup"><span data-stu-id="9bd2b-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span></span>|  
|<span data-ttu-id="9bd2b-118">F</span><span class="sxs-lookup"><span data-stu-id="9bd2b-118">F</span></span>|<span data-ttu-id="9bd2b-119">필드:`Dim`</span><span class="sxs-lookup"><span data-stu-id="9bd2b-119">field: `Dim`</span></span>|  
|<span data-ttu-id="9bd2b-120">P</span><span class="sxs-lookup"><span data-stu-id="9bd2b-120">P</span></span>|<span data-ttu-id="9bd2b-121">속성: `Property` (기본 속성 포함)</span><span class="sxs-lookup"><span data-stu-id="9bd2b-121">property: `Property` (including default properties)</span></span>|  
|<span data-ttu-id="9bd2b-122">M</span><span class="sxs-lookup"><span data-stu-id="9bd2b-122">M</span></span>|<span data-ttu-id="9bd2b-123">method: `Sub`, `Function`, `Declare`,`Operator`</span><span class="sxs-lookup"><span data-stu-id="9bd2b-123">method: `Sub`, `Function`, `Declare`, `Operator`</span></span>|  
|<span data-ttu-id="9bd2b-124">E</span><span class="sxs-lookup"><span data-stu-id="9bd2b-124">E</span></span>|<span data-ttu-id="9bd2b-125">이벤트:`Event`</span><span class="sxs-lookup"><span data-stu-id="9bd2b-125">event: `Event`</span></span>|  
|<span data-ttu-id="9bd2b-126">!</span><span class="sxs-lookup"><span data-stu-id="9bd2b-126">!</span></span>|<span data-ttu-id="9bd2b-127">오류 문자열</span><span class="sxs-lookup"><span data-stu-id="9bd2b-127">error string</span></span><br /><br /> <span data-ttu-id="9bd2b-128">문자열의 나머지 오류에 대 한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="9bd2b-129">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러 링크를 확인할 수 없는 대 한 오류 정보를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-129">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler generates error information for links that cannot be resolved.</span></span>|  
  
-   <span data-ttu-id="9bd2b-130">두 번째 부분에서 `String` 네임 스페이스의 루트에서 시작 하는 항목의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-130">The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="9bd2b-131">항목, 해당 바깥쪽 형식 및 네임 스페이스의 이름은 마침표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-131">The name of the item, its enclosing type(s), and the namespace are separated by periods.</span></span> <span data-ttu-id="9bd2b-132">항목 자체의 이름에 마침표가 있는 경우에 숫자 기호 대체 (#).</span><span class="sxs-lookup"><span data-stu-id="9bd2b-132">If the name of the item itself contains periods, they are replaced by the number sign (#).</span></span> <span data-ttu-id="9bd2b-133">항목이 없는 직접 해당 이름에에서 숫자 기호 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-133">It is assumed that no item has a number sign directly in its name.</span></span> <span data-ttu-id="9bd2b-134">정규화 된 이름에 예를 들어는 `String` 생성자 것 `System.String.#ctor`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-134">For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.</span></span>  
  
-   <span data-ttu-id="9bd2b-135">속성 및 메서드를 메서드에 인수가 있을 경우 괄호 안에 인수 목록을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="9bd2b-136">인수가 있을 경우 없습니다 괄호가 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="9bd2b-137">인수는 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-137">The arguments are separated by commas.</span></span> <span data-ttu-id="9bd2b-138">각 인수의 인코딩은 그대로 따릅니다에서 인코딩하는 방법을 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-138">The encoding of each argument follows directly how it is encoded in a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] signature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bd2b-139">예제</span><span class="sxs-lookup"><span data-stu-id="9bd2b-139">Example</span></span>  
 <span data-ttu-id="9bd2b-140">다음 코드에서는 클래스에 대 한 ID 문자열 방식 하 고 해당 멤버 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd2b-140">The following code shows how the ID strings for a class and its members are generated.</span></span>  
  
 <span data-ttu-id="9bd2b-141">[!code-vb[VbVbcnXmlDocComments #&10;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9bd2b-141">[!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bd2b-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bd2b-142">See Also</span></span>  
 <span data-ttu-id="9bd2b-143">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span><span class="sxs-lookup"><span data-stu-id="9bd2b-143">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span></span>  
<span data-ttu-id="9bd2b-144"> [방법: XML 문서 만들기](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span><span class="sxs-lookup"><span data-stu-id="9bd2b-144"> [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span></span>
