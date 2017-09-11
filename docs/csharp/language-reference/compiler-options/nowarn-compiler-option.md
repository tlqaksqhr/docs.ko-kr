---
title: "-nowarn(C# 컴파일러 옵션)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /nowarn
dev_langs:
- CSharp
helpviewer_keywords:
- nowarn compiler option [C#]
- /nowarn compiler option [C#]
- -nowarn compiler option [C#]
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
caps.latest.revision: 24
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
ms.openlocfilehash: 3bae7e6d16c044b8f1aeba26de434cdf17479e82
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="nowarn-c-compiler-options"></a><span data-ttu-id="b2ac5-102">/nowarn(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="b2ac5-102">/nowarn (C# Compiler Options)</span></span>
<span data-ttu-id="b2ac5-103">**/nowarn** 옵션을 사용하면 컴파일러에서 하나 이상의 경고를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ac5-103">The **/nowarn** option lets you suppress the compiler from displaying one or more warnings.</span></span> <span data-ttu-id="b2ac5-104">여러 경고 번호를 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ac5-104">Separate multiple warning numbers with a comma.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2ac5-105">구문</span><span class="sxs-lookup"><span data-stu-id="b2ac5-105">Syntax</span></span>  
  
```console  
/nowarn:number1[,number2,...]  
```  
  
## <a name="arguments"></a><span data-ttu-id="b2ac5-106">인수</span><span class="sxs-lookup"><span data-stu-id="b2ac5-106">Arguments</span></span>  
 <span data-ttu-id="b2ac5-107">`number1`, `number2`</span><span class="sxs-lookup"><span data-stu-id="b2ac5-107">`number1`, `number2`</span></span>  
 <span data-ttu-id="b2ac5-108">컴파일러에서 표시하지 않으려는 경고 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b2ac5-108">Warning number(s) that you want the compiler to suppress.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2ac5-109">주의</span><span class="sxs-lookup"><span data-stu-id="b2ac5-109">Remarks</span></span>  
 <span data-ttu-id="b2ac5-110">경고 식별자의 숫자 부분만 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ac5-110">You should only specify the numeric part of the warning identifier.</span></span> <span data-ttu-id="b2ac5-111">예를 들어 CS0028을 표시하지 않으려면 `/nowarn:28`을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ac5-111">For example, if you want to suppress CS0028, you could specify `/nowarn:28`.</span></span>  
  
 <span data-ttu-id="b2ac5-112">컴파일러는 이전 릴리스에서 유효했지만 현재 컴파일러에서 제거된, `/nowarn`에 전달된 경고 번호를 자동으로 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ac5-112">The compiler will silently ignore warning numbers passed to `/nowarn` that were valid in previous releases, but that have been removed from the compiler.</span></span> <span data-ttu-id="b2ac5-113">예를 들어 CS0679는 Visual Studio.NET 2002의 컴파일러에서 유효했지만 이후에 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ac5-113">For example, CS0679 was valid in the compiler in Visual Studio .NET 2002 but was subsequently removed.</span></span>  
  
 <span data-ttu-id="b2ac5-114">다음 경고는 `/nowarn` 옵션으로 표시되지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ac5-114">The following warnings cannot be suppressed by the `/nowarn` option:</span></span>  
  
-   <span data-ttu-id="b2ac5-115">컴파일러 경고(수준 1) CS2002</span><span class="sxs-lookup"><span data-stu-id="b2ac5-115">Compiler Warning (level 1) CS2002</span></span>  
  
-   <span data-ttu-id="b2ac5-116">컴파일러 경고(수준 1) CS2023</span><span class="sxs-lookup"><span data-stu-id="b2ac5-116">Compiler Warning (level 1) CS2023</span></span>  
  
-   <span data-ttu-id="b2ac5-117">컴파일러 경고(수준 1) CS2029</span><span class="sxs-lookup"><span data-stu-id="b2ac5-117">Compiler Warning (level 1) CS2029</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="b2ac5-118">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="b2ac5-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="b2ac5-119">프로젝트의 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b2ac5-119">Open the **Properties** page for the project.</span></span> <span data-ttu-id="b2ac5-120">자세한 내용은 [프로젝트 디자이너, 빌드 페이지(C#)](/visualstudio/ide/reference/build-page-project-designer-csharp)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ac5-120">For details, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="b2ac5-121">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ac5-121">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="b2ac5-122">**경고 표시 안 함** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ac5-122">Modify the **Suppress Warnings** property.</span></span>  
  
 <span data-ttu-id="b2ac5-123">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b2ac5-123">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2ac5-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2ac5-124">See Also</span></span>  
 <span data-ttu-id="b2ac5-125">[C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="b2ac5-125">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 <span data-ttu-id="b2ac5-126">[프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties) </span><span class="sxs-lookup"><span data-stu-id="b2ac5-126">[Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties) </span></span>  
 [<span data-ttu-id="b2ac5-127">C# 컴파일러 오류</span><span class="sxs-lookup"><span data-stu-id="b2ac5-127">C# Compiler Errors</span></span>](../../../csharp/language-reference/compiler-messages/index.md)

