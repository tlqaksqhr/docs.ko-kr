---
title: "형식 &#39; &lt;typename&gt;&#39; 정의 되어 있지 않습니다"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords: BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 68eb37f43600c51dc9117c3785a12e3c8ede1965
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="type-39lttypenamegt39-is-not-defined"></a><span data-ttu-id="f524f-102">형식 &#39; &lt;typename&gt;&#39; 정의 되어 있지 않습니다</span><span class="sxs-lookup"><span data-stu-id="f524f-102">Type &#39;&lt;typename&gt;&#39; is not defined</span></span>
<span data-ttu-id="f524f-103">문이 정의 되지 않은 형식에 대 한 참조를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="f524f-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="f524f-104">선언문의 형식을 같은 정의 `Enum`, `Structure`, `Class`, 또는 `Interface`합니다.</span><span class="sxs-lookup"><span data-stu-id="f524f-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="f524f-105">**오류 ID:** BC30002</span><span class="sxs-lookup"><span data-stu-id="f524f-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f524f-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f524f-106">To correct this error</span></span>  
  
-   <span data-ttu-id="f524f-107">형식 정 및 참조 둘 다 사용 하는 동일한 철자를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f524f-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
-   <span data-ttu-id="f524f-108">형식 정의 참조에 액세스할 수 있는지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f524f-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="f524f-109">예를 들어, 형식이 다른 모듈에서 선언 된 경우 `Private`, 참조 하는 모듈로 형식 정의 이동 하거나 선언 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="f524f-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
-   <span data-ttu-id="f524f-110">형식의 네임 스페이스 프로젝트 내에서 다시 정의 되지 않는지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f524f-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="f524f-111">사용 하 여는 `Global` 키워드 형식 이름을 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f524f-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="f524f-112">예를 들어, 명명 된 네임 스페이스를 정의 하는 프로젝트 `System`, <xref:System.Object?displayProperty=nameWithType> 사용 하 여 정규화 하지 않은 형식에 액세스할 수 없습니다는 `Global` 키워드: `Global.System.Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="f524f-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
-   <span data-ttu-id="f524f-113">형식이 정의 되어 있지만 개체 라이브러리 또는 정의 된 형식 라이브러리에 등록 되지 않은 경우 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], 클릭 **참조 추가** 에 **프로젝트** 메뉴를 선택한 후 적절 한 개체 라이브러리 또는 형식 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="f524f-113">If the type is defined, but the object library or type library in which it is defined is not registered in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
-   <span data-ttu-id="f524f-114">대상된.NET Framework 프로필의 일부인 어셈블리에 형식 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f524f-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="f524f-115">자세한 내용은 [.NET Framework 대상 지정 오류 문제 해결](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f524f-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f524f-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f524f-116">See Also</span></span>  
 [<span data-ttu-id="f524f-117">Visual Basic의 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="f524f-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="f524f-118">Enum 문</span><span class="sxs-lookup"><span data-stu-id="f524f-118">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="f524f-119">Structure 문</span><span class="sxs-lookup"><span data-stu-id="f524f-119">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="f524f-120">Class 문</span><span class="sxs-lookup"><span data-stu-id="f524f-120">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="f524f-121">Interface 문</span><span class="sxs-lookup"><span data-stu-id="f524f-121">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="f524f-122">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="f524f-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
