---
title: '&lt;사용 권한&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 4fafebf94be350951672f01f2d17bd00d4bab69a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601997"
---
# <a name="ltpermissiongt-visual-basic"></a><span data-ttu-id="78700-102">&lt;사용 권한&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78700-102">&lt;permission&gt; (Visual Basic)</span></span>
<span data-ttu-id="78700-103">멤버에 대 한 필요한 사용 권한을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78700-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78700-104">구문</span><span class="sxs-lookup"><span data-stu-id="78700-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="78700-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="78700-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="78700-106">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="78700-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="78700-107">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="78700-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="78700-108">묶습니다 `member` 큰따옴표에서 ("").</span><span class="sxs-lookup"><span data-stu-id="78700-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="78700-109">멤버 액세스 권한에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="78700-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78700-110">설명</span><span class="sxs-lookup"><span data-stu-id="78700-110">Remarks</span></span>  
 <span data-ttu-id="78700-111">사용 하 여는 `<permission>` 태그를 멤버의 액세스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="78700-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="78700-112">사용 된 <xref:System.Security.PermissionSet> 클래스 멤버에 대 한 액세스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78700-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="78700-113">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="78700-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78700-114">예제</span><span class="sxs-lookup"><span data-stu-id="78700-114">Example</span></span>  
 <span data-ttu-id="78700-115">사용 하 여이 예제는 `<permission>` 태그를 설명 하는 <xref:System.Security.Permissions.FileIOPermission> 에 필요한는 `ReadFile` 메서드.</span><span class="sxs-lookup"><span data-stu-id="78700-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="78700-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78700-116">See Also</span></span>  
 [<span data-ttu-id="78700-117">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="78700-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
