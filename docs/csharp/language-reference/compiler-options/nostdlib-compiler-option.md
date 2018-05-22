---
title: -nostdlib(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 1dc0ab70ca28626c4a3f505c13ec1d6f828a4b05
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-nostdlib-c-compiler-options"></a><span data-ttu-id="bc079-102">-nostdlib(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="bc079-102">-nostdlib (C# Compiler Options)</span></span>
<span data-ttu-id="bc079-103">**-nostdlib**를 사용하면 전체 시스템 네임스페이스를 정의하는 mscorlib.dll을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc079-103">**-nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc079-104">구문</span><span class="sxs-lookup"><span data-stu-id="bc079-104">Syntax</span></span>  
  
```console  
-nostdlib[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="bc079-105">설명</span><span class="sxs-lookup"><span data-stu-id="bc079-105">Remarks</span></span>  
 <span data-ttu-id="bc079-106">고유한 시스템 네임스페이스와 개체를 정의하거나 만들려면 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bc079-106">Use this option if you want to define or create your own System namespace and objects.</span></span>  
  
 <span data-ttu-id="bc079-107">**-nostdlib**를 지정하지 않으면 mscorlib.dll을 프로그램으로 가져옵니다( **-nostdlib-** 지정과 동일함).</span><span class="sxs-lookup"><span data-stu-id="bc079-107">If you do not specify **-nostdlib**, mscorlib.dll will be imported into your program (same as specifying **-nostdlib-**).</span></span> <span data-ttu-id="bc079-108">**-nostdlib**를 지정하는 것은 **-nostdlib+** 를 지정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bc079-108">Specifying **-nostdlib** is the same as specifying **-nostdlib+**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="bc079-109">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="bc079-109">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="bc079-110">프로젝트의 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bc079-110">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="bc079-111">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bc079-111">Click the **Build** properties page.</span></span>  
  
3.  <span data-ttu-id="bc079-112">**고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bc079-112">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="bc079-113">**mscorlib.dll을 참조하지 않음** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc079-113">Modify the **Do not reference mscorlib.dll** property.</span></span>  
  
 <span data-ttu-id="bc079-114">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc079-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc079-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc079-115">See Also</span></span>  
 [<span data-ttu-id="bc079-116">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="bc079-116">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
