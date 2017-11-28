---
title: "-unsafe(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.assetid: fdb77ed9-da03-45bd-bb7f-250704da1bcc
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 146977522b400418a26f6a83e1a0ccdca8675bf9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="unsafe-c-compiler-options"></a><span data-ttu-id="8da78-102">/unsafe(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="8da78-102">/unsafe (C# Compiler Options)</span></span>
<span data-ttu-id="8da78-103">**/unsafe** 컴파일러 옵션을 사용하면 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 키워드를 사용하는 코드를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8da78-103">The **/unsafe** compiler option allows code that uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8da78-104">구문</span><span class="sxs-lookup"><span data-stu-id="8da78-104">Syntax</span></span>  
  
```console  
/unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="8da78-105">설명</span><span class="sxs-lookup"><span data-stu-id="8da78-105">Remarks</span></span>  
 <span data-ttu-id="8da78-106">안전하지 않은 코드에 대한 자세한 내용은 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8da78-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="8da78-107">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="8da78-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="8da78-108">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8da78-108">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="8da78-109">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8da78-109">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="8da78-110">**안전하지 않은 코드 허용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8da78-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
 <span data-ttu-id="8da78-111">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8da78-111">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8da78-112">예제</span><span class="sxs-lookup"><span data-stu-id="8da78-112">Example</span></span>  
 <span data-ttu-id="8da78-113">안전하지 않은 모드에 대해 `in.cs` 컴파일:</span><span class="sxs-lookup"><span data-stu-id="8da78-113">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc /unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="8da78-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8da78-114">See Also</span></span>  
 [<span data-ttu-id="8da78-115">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="8da78-115">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="8da78-116">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="8da78-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
