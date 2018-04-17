---
title: '방법: 형식 라이브러리에 참조 추가'
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 561e05c82c1882ad5e495ddb3dc1a17356522514
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-references-to-type-libraries"></a><span data-ttu-id="83615-102">방법: 형식 라이브러리에 참조 추가</span><span class="sxs-lookup"><span data-stu-id="83615-102">How to: Add References to Type Libraries</span></span>
<span data-ttu-id="83615-103">Visual Studio에서는 형식 라이브러리에 참조를 추가하면 메타데이터가 포함된 interop 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="83615-103">Visual Studio generates an interop assembly containing metadata when you add a reference to a type library.</span></span> <span data-ttu-id="83615-104">주 interop 어셈블리를 사용할 수 있는 경우 Visual Studio는 새 interop 어셈블리를 생성하기 전에 기존 어셈블리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83615-104">If a primary interop assembly is available, Visual Studio uses the existing assembly before generating a new interop assembly.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a><span data-ttu-id="83615-105">Visual Studio에서 형식 라이브러리에 대한 참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="83615-105">To add a reference to a type library in Visual Studio</span></span>  
  
1.  <span data-ttu-id="83615-106">Windows Setup.exe 파일이 자동으로 설치를 수행하는 경우가 아니라면 컴퓨터에 COM DLL 또는 EXE 파일을 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="83615-106">Install the COM DLL or EXE file on your computer, unless a Windows Setup.exe file performs the installation for you.</span></span>  
  
2.  <span data-ttu-id="83615-107">**프로젝트**, **참조 추가**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83615-107">Choose **Project**, **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="83615-108">참조 관리자에서 **COM**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83615-108">In the Reference Manager, choose **COM**.</span></span>  
  
4.  <span data-ttu-id="83615-109">목록에서 형식 라이브러리를 선택하거나 .tlb 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="83615-109">Select the type library from the list, or browse for the .tlb file.</span></span>  
  
5.  <span data-ttu-id="83615-110">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83615-110">Choose **OK**.</span></span>  
  
6.  <span data-ttu-id="83615-111">솔루션 탐색기에서 방금 추가한 참조에 대한 바로 가기 메뉴를 열고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83615-111">In Solution Explorer, open the shortcut menu for the reference you just added, and then choose **Properties**.</span></span>  
  
7.  <span data-ttu-id="83615-112">**속성** 창에서 **Interop 형식 포함** 속성이 **True**로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="83615-112">In the **Properties** window, make sure that the **Embed Interop Types** property is set to **True**.</span></span> <span data-ttu-id="83615-113">이 경우 Visual Studio가 COM 형식에 대한 형식 정보를 실행 파일에 포함하므로 앱과 함께 주 interop 어셈블리를 배포할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83615-113">This causes Visual Studio to embed type information for COM types in your executables, eliminating the need to deploy primary interop assemblies with your app.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83615-114">메뉴 및 대화 상자 옵션은 사용 중인 Visual Studio 버전에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83615-114">The menu and dialog box options may vary depending on the version of Visual Studio you're using.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a><span data-ttu-id="83615-115">명령줄 컴파일용으로 형식 라이브러리에 대한 참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="83615-115">To add a reference to a type library for command-line compilation</span></span>  
  
1.  <span data-ttu-id="83615-116">[방법: 형식 라이브러리에서 Interop 어셈블리 생성](how-to-generate-interop-assemblies-from-type-libraries.md)의 설명에 따라 interop 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="83615-116">Generate an interop assembly as described in [How to: Generate Interop Assemblies from Type Libraries](how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
2.  <span data-ttu-id="83615-117">interop 어셈블리 이름을 포함한 [/link(C# 컴파일러 옵션)](../../csharp/language-reference/compiler-options/link-compiler-option.md) 또는 [/link(Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) 컴파일러 옵션을 사용하여 COM 형식에 대한 형식 정보를 실행 파일에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="83615-117">Use the [/link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler option with the interop assembly name to embed type information for COM types in your executables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83615-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83615-118">See Also</span></span>  
 [<span data-ttu-id="83615-119">형식 라이브러리를 어셈블리로 가져오기</span><span class="sxs-lookup"><span data-stu-id="83615-119">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)  
 [<span data-ttu-id="83615-120">.NET Framework에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="83615-120">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)  
 <span data-ttu-id="83615-121">[연습: Microsoft Office 어셈블리의 형식 정보 포함](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="83615-121">[Walkthrough: Embedding Type Information from Microsoft Office Assemblies](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))</span></span>  
 [<span data-ttu-id="83615-122">연습: 관리되는 어셈블리의 형식 포함</span><span class="sxs-lookup"><span data-stu-id="83615-122">Walkthrough: Embedding Types from Managed Assemblies</span></span>](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [<span data-ttu-id="83615-123">/link(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="83615-123">/link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)  
 [<span data-ttu-id="83615-124">/link(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83615-124">/link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
