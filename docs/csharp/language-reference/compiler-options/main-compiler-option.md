---
title: "-main(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5f1d06bf408f13a78df503ab10fe3c57b4ff68a3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="c406c-102">-main(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="c406c-102">-main (C# Compiler Options)</span></span>
<span data-ttu-id="c406c-103">이 옵션은 둘 이상의 클래스에 **Main** 메서드가 포함된 경우 프로그램에 대한 진입점을 포함하는 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c406c-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c406c-104">구문</span><span class="sxs-lookup"><span data-stu-id="c406c-104">Syntax</span></span>  
  
```console  
-main:class  
```  
  
## <a name="arguments"></a><span data-ttu-id="c406c-105">인수</span><span class="sxs-lookup"><span data-stu-id="c406c-105">Arguments</span></span>  
 `class`  
 <span data-ttu-id="c406c-106">**Main** 메서드를 포함하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c406c-106">The type that contains the **Main** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c406c-107">설명</span><span class="sxs-lookup"><span data-stu-id="c406c-107">Remarks</span></span>  
 <span data-ttu-id="c406c-108">컴파일에 [Main](../../../csharp/programming-guide/main-and-command-args/index.md) 메서드가 있는 형식이 둘 이상 포함된 경우 프로그램에 대한 진입점으로 사용할 **Main** 메서드를 포함하는 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c406c-108">If your compilation includes more than one type with a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>  
  
 <span data-ttu-id="c406c-109">이 옵션은 .exe 파일을 컴파일할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c406c-109">This option is for use when compiling an .exe file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="c406c-110">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="c406c-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="c406c-111">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c406c-111">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="c406c-112">**응용 프로그램** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c406c-112">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="c406c-113">**시작 개체** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="c406c-113">Modify the **Startup object** property.</span></span>  
  
     <span data-ttu-id="c406c-114">프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면 <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c406c-114">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c406c-115">예</span><span class="sxs-lookup"><span data-stu-id="c406c-115">Example</span></span>  
 <span data-ttu-id="c406c-116">**Main** 메서드가 `Test2`에 있다고 지정하여 `t2.cs` 및 `t3.cs`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="c406c-116">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>  
  
```console  
csc t2.cs t3.cs -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="c406c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c406c-117">See Also</span></span>  
 [<span data-ttu-id="c406c-118">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="c406c-118">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="c406c-119">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="c406c-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
