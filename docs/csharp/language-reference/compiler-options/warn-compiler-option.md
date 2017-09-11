---
title: "-warn(C# 컴파일러 옵션)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /warn
dev_langs:
- CSharp
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
caps.latest.revision: 17
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
ms.openlocfilehash: e703060b7cc5f897ddf0b6764e9607460666e92c
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="warn-c-compiler-options"></a><span data-ttu-id="84d44-102">/warn(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="84d44-102">/warn (C# Compiler Options)</span></span>
<span data-ttu-id="84d44-103">**/warn** 옵션은 컴파일러에서 표시할 경고 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="84d44-103">The **/warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84d44-104">구문</span><span class="sxs-lookup"><span data-stu-id="84d44-104">Syntax</span></span>  
  
```console  
/warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="84d44-105">인수</span><span class="sxs-lookup"><span data-stu-id="84d44-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="84d44-106">컴파일에 대해 표시할 경고 수준입니다. 숫자가 낮으면 높은 심각도 경고만 표시되고, 숫자가 높으면 더 많은 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="84d44-106">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="84d44-107">유효한 값은 0-4입니다.</span><span class="sxs-lookup"><span data-stu-id="84d44-107">Valid values are 0-4:</span></span>  
  
|<span data-ttu-id="84d44-108">경고 수준</span><span class="sxs-lookup"><span data-stu-id="84d44-108">Warning level</span></span>|<span data-ttu-id="84d44-109">의미</span><span class="sxs-lookup"><span data-stu-id="84d44-109">Meaning</span></span>|  
|-------------------|-------------|  
|<span data-ttu-id="84d44-110">0</span><span class="sxs-lookup"><span data-stu-id="84d44-110">0</span></span>|<span data-ttu-id="84d44-111">모든 경고 메시지 내보내기를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="84d44-111">Turns off emission of all warning messages.</span></span>|  
|<span data-ttu-id="84d44-112">1</span><span class="sxs-lookup"><span data-stu-id="84d44-112">1</span></span>|<span data-ttu-id="84d44-113">심각한 경고 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="84d44-113">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="84d44-114">2</span><span class="sxs-lookup"><span data-stu-id="84d44-114">2</span></span>|<span data-ttu-id="84d44-115">수준 1 경고와 덜 심각한 특정 경고(예: 클래스 멤버 숨기기에 대한 경고)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="84d44-115">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="84d44-116">3</span><span class="sxs-lookup"><span data-stu-id="84d44-116">3</span></span>|<span data-ttu-id="84d44-117">수준 2 경고와 덜 심각한 특정 경고(예: 항상 `true` 또는 `false`로 평가되는 식에 대한 경고)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="84d44-117">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="84d44-118">4(기본값)</span><span class="sxs-lookup"><span data-stu-id="84d44-118">4 (the default)</span></span>|<span data-ttu-id="84d44-119">모든 수준 3 경고와 정보 경고를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="84d44-119">Displays all level 3 warnings plus informational warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84d44-120">설명</span><span class="sxs-lookup"><span data-stu-id="84d44-120">Remarks</span></span>  
 <span data-ttu-id="84d44-121">오류 또는 경고에 대한 정보를 가져오려면 도움말 색인에서 오류 코드를 조회할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d44-121">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="84d44-122">오류 또는 경고에 대한 정보를 가져오는 다른 방법은 [C# 컴파일러 오류](../../../csharp/language-reference/compiler-messages/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84d44-122">For other ways to get information about an error or warning, see [C# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="84d44-123">모든 경고를 오류로 처리하려면 [/warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84d44-123">Use [/warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="84d44-124">특정 경고를 사용하지 않으려면 [/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84d44-124">Use [/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="84d44-125">**/w**는 **/warn**의 약식 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="84d44-125">**/w** is the short form of **/warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="84d44-126">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="84d44-126">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="84d44-127">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="84d44-127">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="84d44-128">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="84d44-128">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="84d44-129">**경고 수준** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="84d44-129">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="84d44-130">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84d44-130">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84d44-131">예제</span><span class="sxs-lookup"><span data-stu-id="84d44-131">Example</span></span>  
 <span data-ttu-id="84d44-132">`in.cs`를 컴파일하고 컴파일러에서 수준 1 경고만 표시하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d44-132">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc /warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="84d44-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84d44-133">See Also</span></span>  
 <span data-ttu-id="84d44-134">[C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="84d44-134">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="84d44-135">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="84d44-135">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

