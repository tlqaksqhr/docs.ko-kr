---
title: "-define(C# 컴파일러 옵션)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /define
dev_langs:
- CSharp
helpviewer_keywords:
- -define compiler option [C#]
- /define compiler option [C#]
- -d compiler option [C#]
- define compiler option [C#]
- /d compiler option [C#]
- d compiler option [C#]
ms.assetid: f17d7b4d-82d0-4133-8563-68cced1cac6e
caps.latest.revision: 21
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
ms.openlocfilehash: dbe5532114864d9f76c6d9e19b669c46489709b2
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="define-c-compiler-options"></a><span data-ttu-id="17fd0-102">/define(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="17fd0-102">/define (C# Compiler Options)</span></span>
<span data-ttu-id="17fd0-103">**/define** 옵션은 프로그램의 모든 소스 코드 파일에서 `name`을 기호로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="17fd0-103">The **/define** option defines `name` as a symbol in all source code files your program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17fd0-104">구문</span><span class="sxs-lookup"><span data-stu-id="17fd0-104">Syntax</span></span>  
  
```console  
/define:name[;name2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="17fd0-105">인수</span><span class="sxs-lookup"><span data-stu-id="17fd0-105">Arguments</span></span>  
 <span data-ttu-id="17fd0-106">`name`, `name2`</span><span class="sxs-lookup"><span data-stu-id="17fd0-106">`name`, `name2`</span></span>  
 <span data-ttu-id="17fd0-107">정의하려는 하나 이상의 기호 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="17fd0-107">The name of one or more symbols that you want to define.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17fd0-108">설명</span><span class="sxs-lookup"><span data-stu-id="17fd0-108">Remarks</span></span>  
 <span data-ttu-id="17fd0-109">**/define** 옵션은 컴파일러 옵션의 경우 프로젝트의 모든 파일에 적용된다는 점을 제외하고 [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) 전처리기 지시문을 사용하는 것과 효과가 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="17fd0-109">The **/define** option has the same effect as using a [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive except that the compiler option is in effect for all files in the project.</span></span> <span data-ttu-id="17fd0-110">소스 파일의 [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) 지시문이 정의를 제거할 때까지 기호는 소스 파일에 정의된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="17fd0-110">A symbol remains defined in a source file until an [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) directive in the source file removes the definition.</span></span> <span data-ttu-id="17fd0-111">/define 옵션을 사용하는 경우 한 파일의 `#undef` 지시문이 프로젝트의 다른 소스 코드 파일에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17fd0-111">When you use the /define option, an `#undef` directive in one file has no effect on other source code files in the project.</span></span>  
  
 <span data-ttu-id="17fd0-112">이 옵션으로 만든 기호를 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)와 함께 사용하면 소스 파일을 조건부 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17fd0-112">You can use symbols created by this option with [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), and [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="17fd0-113">**/d**는 **/define**의 약식 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="17fd0-113">**/d** is the short form of **/define**.</span></span>  
  
 <span data-ttu-id="17fd0-114">세미콜론 또는 쉼표를 사용해서 기호 이름을 구분하여 **/define**으로 여러 기호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17fd0-114">You can define multiple symbols with **/define** by using a semicolon or comma to separate symbol names.</span></span> <span data-ttu-id="17fd0-115">예:</span><span class="sxs-lookup"><span data-stu-id="17fd0-115">For example:</span></span>  
  
```console  
/define:DEBUG;TUESDAY  
```  
  
 <span data-ttu-id="17fd0-116">C# 컴파일러 자체는 소스 코드에서 사용할 수 있는 기호 또는 매크로를 정의하지 않습니다. 모든 기호 정의는 사용자가 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17fd0-116">The C# compiler itself defines no symbols or macros that you can use in your source code; all symbol definitions must be user-defined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17fd0-117">C# `#define`에서는 C++와 같은 언어에서처럼 기호에 값을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17fd0-117">The C# `#define` does not allow a symbol to be given a value, as in languages such as C++.</span></span> <span data-ttu-id="17fd0-118">예를 들어 `#define`을 사용하여 매크로를 만들거나 상수를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17fd0-118">For example, `#define` cannot be used to create a macro or to define a constant.</span></span> <span data-ttu-id="17fd0-119">상수를 정의해야 하는 경우 `enum` 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="17fd0-119">If you need to define a constant, use an `enum` variable.</span></span> <span data-ttu-id="17fd0-120">C++ 스타일 매크로를 만들려는 경우 제네릭과 같은 다른 방식을 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="17fd0-120">If you want to create a C++ style macro, consider alternatives such as generics.</span></span> <span data-ttu-id="17fd0-121">매크로는 오류가 발생할 가능성이 크므로 C#에서는 매크로를 사용할 수 없으며 더 안전한 방식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="17fd0-121">Since macros are notoriously error-prone, C# disallows their use but provides safer alternatives.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="17fd0-122">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="17fd0-122">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="17fd0-123">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="17fd0-123">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="17fd0-124">**빌드** 탭의 **조건부 컴파일 기호** 상자에 정의할 기호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="17fd0-124">On the **Build** tab, type the symbol that is to be defined in the **Conditional compilation symbols** box.</span></span> <span data-ttu-id="17fd0-125">예를 들어 다음 코드 예제를 사용하는 경우 텍스트 상자에 `xx`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="17fd0-125">For example, if you are using the code example that follows, just type `xx` into the text box.</span></span>  
  
 <span data-ttu-id="17fd0-126">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="17fd0-126">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17fd0-127">예제</span><span class="sxs-lookup"><span data-stu-id="17fd0-127">Example</span></span>  
  
```csharp  
// preprocessor_define.cs  
// compile with: /define:xx  
// or uncomment the next line  
// #define xx  
using System;  
public class Test   
{  
    public static void Main()   
    {  
        #if (xx)   
            Console.WriteLine("xx defined");  
        #else  
            Console.WriteLine("xx not defined");  
        #endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="17fd0-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17fd0-128">See Also</span></span>  
 <span data-ttu-id="17fd0-129">[C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="17fd0-129">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="17fd0-130">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="17fd0-130">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

