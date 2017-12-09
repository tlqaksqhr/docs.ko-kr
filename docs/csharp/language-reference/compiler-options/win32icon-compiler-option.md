---
title: "-win32icon(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 356502b8528e22a5b5ff9a28a3f82d5f9c0a72f9
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/06/2017
---
# <a name="win32icon-c-compiler-options"></a><span data-ttu-id="16343-102">/win32icon(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="16343-102">/win32icon (C# Compiler Options)</span></span>
<span data-ttu-id="16343-103">**/win32icon** 옵션은 .ico 파일을 출력 파일에 삽입하여 파일 탐색기에서 출력 파일을 원하는 모양으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="16343-103">The **/win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16343-104">구문</span><span class="sxs-lookup"><span data-stu-id="16343-104">Syntax</span></span>  
  
```console  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="16343-105">인수</span><span class="sxs-lookup"><span data-stu-id="16343-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="16343-106">출력 파일에 추가하려는 .ico 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="16343-106">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16343-107">설명</span><span class="sxs-lookup"><span data-stu-id="16343-107">Remarks</span></span>  
 <span data-ttu-id="16343-108">.ico 파일은 [리소스 컴파일러](https://msdn.microsoft.com/library/aa381042.aspx)로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16343-108">An .ico file can be created with the [Resource Compiler](https://msdn.microsoft.com/library/aa381042.aspx).</span></span> <span data-ttu-id="16343-109">리소스 컴파일러는 Visual C++ 프로그램을 컴파일할 때 실행되며 .rc 파일에서 .iso 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="16343-109">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="16343-110">.NET Framework 리소스 파일을 참조하려면 [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md)를, 첨부하려면 [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16343-110">See [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (to reference) or [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="16343-111">.res 파일을 가져오려면 [/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16343-111">See [/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="16343-112">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="16343-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="16343-113">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="16343-113">Open the project's **Properties** pages.</span></span>  
  
2.  <span data-ttu-id="16343-114">**응용 프로그램** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="16343-114">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="16343-115">**응용 프로그램 아이콘** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="16343-115">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="16343-116">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16343-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16343-117">예제</span><span class="sxs-lookup"><span data-stu-id="16343-117">Example</span></span>  
 <span data-ttu-id="16343-118">`in.cs`를 컴파일하고 .ico 파일 `rf.ico`를 첨부하여 `in.exe`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="16343-118">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc /win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="16343-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16343-119">See Also</span></span>  
 [<span data-ttu-id="16343-120">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="16343-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="16343-121">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="16343-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
