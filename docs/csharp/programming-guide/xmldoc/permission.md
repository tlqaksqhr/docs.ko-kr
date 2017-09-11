---
title: "&lt;permission&gt;(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- permission
- <permission>
dev_langs:
- CSharp
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4b8f109d7e01f6e630f09939161b6a20c3a13f73
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="ltpermissiongt-c-programming-guide"></a><span data-ttu-id="c15c7-102">&lt;permission&gt;(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="c15c7-102">&lt;permission&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="c15c7-103">구문</span><span class="sxs-lookup"><span data-stu-id="c15c7-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c15c7-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c15c7-104">Parameters</span></span>  
 <span data-ttu-id="c15c7-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="c15c7-105">cref = " `member`"</span></span>  
 <span data-ttu-id="c15c7-106">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="c15c7-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="c15c7-107">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c15c7-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="c15c7-108">*member*는 큰따옴표(“ ”)로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15c7-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="c15c7-109">제네릭 형식에 대한 cref 참조를 만드는 방법에 대한 자세한 내용은 [\<see>](../../../csharp/programming-guide/xmldoc/see.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c15c7-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="c15c7-110">멤버 액세스 권한에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="c15c7-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c15c7-111">설명</span><span class="sxs-lookup"><span data-stu-id="c15c7-111">Remarks</span></span>  
 <span data-ttu-id="c15c7-112">\<permission> 태그를 사용하면 멤버 액세스 권한을 문서화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15c7-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="c15c7-113"><xref:System.Security.PermissionSet> 클래스를 사용하면 멤버 액세스 권한을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15c7-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="c15c7-114">[/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c15c7-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c15c7-115">예제</span><span class="sxs-lookup"><span data-stu-id="c15c7-115">Example</span></span>  
 <span data-ttu-id="c15c7-116">[!code-cs[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c15c7-116">[!code-cs[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c15c7-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c15c7-117">See Also</span></span>  
 <span data-ttu-id="c15c7-118">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c15c7-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="c15c7-119">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="c15c7-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

