---
title: XML 파일 처리(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 6be7597f1c03d8aa044eba70ef6287cfc07d9b84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652040"
---
# <a name="processing-the-xml-file-visual-basic"></a><span data-ttu-id="37888-102">XML 파일 처리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37888-102">Processing the XML File (Visual Basic)</span></span>
<span data-ttu-id="37888-103">컴파일러는 문서 생성을 위해 태그가 지정되는 코드의 각 구문에 대해 ID 문자열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="37888-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="37888-104">(코드에 태그를 하는 방법에 대 한 정보를 참조 하십시오. [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) ID 문자열은 구문을 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="37888-104">(For information on how to tag your code, see [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="37888-105">XML 파일을 처리 하는 프로그램 해당 식별 하는 ID 문자열을 사용할 수 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 메타 데이터/리플렉션 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="37888-105">Programs that process the XML file can use the ID string to identify the corresponding [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] metadata/reflection item.</span></span>  
  
 <span data-ttu-id="37888-106">XML 파일의 코드; 계층적 나타내지는 않습니다. 각 요소에 대해 생성된 된 ID로 단순 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="37888-106">The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.</span></span>  
  
 <span data-ttu-id="37888-107">컴파일러는 ID 문자열을 생성할 때 다음 규칙을 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="37888-107">The compiler observes the following rules when it generates the ID strings:</span></span>  
  
-   <span data-ttu-id="37888-108">문자열에 공백이 없습니다 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37888-108">No white space is placed in the string.</span></span>  
  
-   <span data-ttu-id="37888-109">ID 문자열의 첫 번째 부분 뒤에 콜론을 단일 문자로 식별 되 고 멤버의 종류를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="37888-109">The first part of the ID string identifies the kind of member being identified, with a single character followed by a colon.</span></span> <span data-ttu-id="37888-110">다음과 같은 멤버 형식은 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="37888-110">The following member types are used.</span></span>  
  
|<span data-ttu-id="37888-111">문자</span><span class="sxs-lookup"><span data-stu-id="37888-111">Character</span></span>|<span data-ttu-id="37888-112">설명</span><span class="sxs-lookup"><span data-stu-id="37888-112">Description</span></span>|  
|---|---|  
|<span data-ttu-id="37888-113">N</span><span class="sxs-lookup"><span data-stu-id="37888-113">N</span></span>|<span data-ttu-id="37888-114">네임스페이스(namespace)</span><span class="sxs-lookup"><span data-stu-id="37888-114">namespace</span></span><br /><br /> <span data-ttu-id="37888-115">네임 스페이스 문서 주석을 추가할 수 없지만, CREF 참조를 만들 수 있습니다 지원 되는 경우.</span><span class="sxs-lookup"><span data-stu-id="37888-115">You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.</span></span>|  
|<span data-ttu-id="37888-116">T</span><span class="sxs-lookup"><span data-stu-id="37888-116">T</span></span>|<span data-ttu-id="37888-117">형식: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span><span class="sxs-lookup"><span data-stu-id="37888-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span></span>|  
|<span data-ttu-id="37888-118">F</span><span class="sxs-lookup"><span data-stu-id="37888-118">F</span></span>|<span data-ttu-id="37888-119">필드: `Dim`</span><span class="sxs-lookup"><span data-stu-id="37888-119">field: `Dim`</span></span>|  
|<span data-ttu-id="37888-120">P</span><span class="sxs-lookup"><span data-stu-id="37888-120">P</span></span>|<span data-ttu-id="37888-121">속성: `Property` (기본 속성 포함)</span><span class="sxs-lookup"><span data-stu-id="37888-121">property: `Property` (including default properties)</span></span>|  
|<span data-ttu-id="37888-122">M</span><span class="sxs-lookup"><span data-stu-id="37888-122">M</span></span>|<span data-ttu-id="37888-123">방법: `Sub`, `Function`, `Declare`, `Operator`</span><span class="sxs-lookup"><span data-stu-id="37888-123">method: `Sub`, `Function`, `Declare`, `Operator`</span></span>|  
|<span data-ttu-id="37888-124">E</span><span class="sxs-lookup"><span data-stu-id="37888-124">E</span></span>|<span data-ttu-id="37888-125">이벤트: `Event`</span><span class="sxs-lookup"><span data-stu-id="37888-125">event: `Event`</span></span>|  
|<span data-ttu-id="37888-126">!</span><span class="sxs-lookup"><span data-stu-id="37888-126">!</span></span>|<span data-ttu-id="37888-127">오류 문자열</span><span class="sxs-lookup"><span data-stu-id="37888-127">error string</span></span><br /><br /> <span data-ttu-id="37888-128">문자열의 나머지 부분은 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37888-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="37888-129">Visual Basic 컴파일러는 확인할 수 없는 링크에 대 한 오류 정보를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="37888-129">The Visual Basic compiler generates error information for links that cannot be resolved.</span></span>|  
  
-   <span data-ttu-id="37888-130">두 번째 부분에서 `String` 네임 스페이스의 루트에서 시작 하는 항목의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="37888-130">The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="37888-131">이름, 해당 바깥쪽 형식 항목과의 네임 스페이스는 마침표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37888-131">The name of the item, its enclosing type(s), and the namespace are separated by periods.</span></span> <span data-ttu-id="37888-132">항목 이름에 마침표가 하는 경우에 숫자 기호 대체 (#).</span><span class="sxs-lookup"><span data-stu-id="37888-132">If the name of the item itself contains periods, they are replaced by the number sign (#).</span></span> <span data-ttu-id="37888-133">항목이 직접 이름에에서 숫자 기호 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37888-133">It is assumed that no item has a number sign directly in its name.</span></span> <span data-ttu-id="37888-134">정규화 된 이름 예를 들어는 `String` 생성자 것 `System.String.#ctor`합니다.</span><span class="sxs-lookup"><span data-stu-id="37888-134">For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.</span></span>  
  
-   <span data-ttu-id="37888-135">속성 및 메서드의 경우 메서드에 대한 인수가 있으면 괄호로 묶인 인수 목록이 문자열 뒤에 붙습니다.</span><span class="sxs-lookup"><span data-stu-id="37888-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="37888-136">인수가 없으면 괄호도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37888-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="37888-137">인수는 쉼표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="37888-137">The arguments are separated by commas.</span></span> <span data-ttu-id="37888-138">각 인수의 인코딩은 뒤에 오는 직접에서 인코딩하는 방법을 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="37888-138">The encoding of each argument follows directly how it is encoded in a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] signature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37888-139">예제</span><span class="sxs-lookup"><span data-stu-id="37888-139">Example</span></span>  
 <span data-ttu-id="37888-140">다음 코드는 클래스에 대 한 ID 문자열 하는 방법을 보여 줍니다. 및 해당 멤버 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37888-140">The following code shows how the ID strings for a class and its members are generated.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="37888-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37888-141">See Also</span></span>  
 [<span data-ttu-id="37888-142">/doc</span><span class="sxs-lookup"><span data-stu-id="37888-142">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [<span data-ttu-id="37888-143">방법: XML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="37888-143">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
