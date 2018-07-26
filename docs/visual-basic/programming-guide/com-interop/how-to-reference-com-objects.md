---
title: '방법: Visual Basic에서 COM 개체 참조'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: 49f3da396ca5cd48b0cf454ce1ecd5422c28e38f
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39199367"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="52021-102">방법: Visual Basic에서 COM 개체 참조</span><span class="sxs-lookup"><span data-stu-id="52021-102">How to: Reference COM Objects from Visual Basic</span></span>
<span data-ttu-id="52021-103">Visual basic의 경우 형식 라이브러리가 포함 된 COM 개체에 대 한 참조를 추가 합니다. COM 라이브러리에 대 한 interop 어셈블리를 만들이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="52021-103">In Visual Basic, adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="52021-104">COM 개체의 멤버에 대 한 참조는 interop 어셈블리에 라우팅되어 실제 COM 개체에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52021-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="52021-105">Interop 어셈블리에 COM 개체의 응답은 라우팅되고 전달할 프로그램 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="52021-105">Responses from the COM object are routed to the interop assembly and forwarded to your [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] application.</span></span>  
  
 <span data-ttu-id="52021-106">.NET 어셈블리에 COM 개체에 대 한 형식 정보를 포함 하 여 interop 어셈블리를 사용 하지 않고 COM 개체를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52021-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="52021-107">형식 정보를 포함 하려면 설정 합니다 `Embed Interop Types` 속성을 `True` COM 개체에 대 한 참조에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="52021-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="52021-108">명령줄 컴파일러를 사용 하 여 컴파일할 경우 사용 된 `/link` COM 라이브러리를 참조 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="52021-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="52021-109">자세한 내용은 [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="52021-109">For more information, see [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span></span>  
  
 <span data-ttu-id="52021-110">통합된 개발 환경 (IDE)에서 형식 라이브러리에 대 한 참조를 추가 하면 Visual Basic interop 어셈블리를 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="52021-110">Visual Basic automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="52021-111">명령줄에서 작업을 하는 경우 interop 어셈블리를 수동으로 만들려면 Tlbimp 유틸리티를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52021-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="52021-112">COM 개체에 대 한 참조를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="52021-112">To add references to COM objects</span></span>  
  
1.  <span data-ttu-id="52021-113">에 **프로젝트** 메뉴 선택 **참조 추가** 클릭 하 고는 **COM** 대화 상자에서 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="52021-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2.  <span data-ttu-id="52021-114">COM 개체의 목록에서 사용 하려는 구성 요소를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="52021-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3.  <span data-ttu-id="52021-115">Interop 어셈블리에 대 한 액세스를 간소화 하려면 추가 `Imports` 문을 클래스 또는는 COM 개체를 사용 하는 모듈의 맨 위로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="52021-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="52021-116">예를 들어, 다음 코드 예제에서는 네임 스페이스를 가져옵니다 `INKEDLib` 에서 참조 되는 개체는 `Microsoft InkEdit Control 1.0` 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="52021-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="52021-117">Tlbimp를 사용 하 여 interop 어셈블리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="52021-117">To create an interop assembly using Tlbimp</span></span>  
  
1.  <span data-ttu-id="52021-118">이미 속하지 않는의 검색 경로 및 현재 위치한 디렉터리 하지 않는 경우 검색 경로에 Tlbimp의 위치를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="52021-118">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2.  <span data-ttu-id="52021-119">다음 정보를 제공 하는 명령 프롬프트에서 Tlbimp를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="52021-119">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    -   <span data-ttu-id="52021-120">형식 라이브러리를 포함 하는 DLL의 이름 및 위치</span><span class="sxs-lookup"><span data-stu-id="52021-120">Name and location of the DLL that contains the type library</span></span>  
  
    -   <span data-ttu-id="52021-121">이름 및 네임 스페이스 정보를 배치할 위치</span><span class="sxs-lookup"><span data-stu-id="52021-121">Name and location of the namespace where the information should be placed</span></span>  
  
    -   <span data-ttu-id="52021-122">대상 interop 어셈블리의 이름 및 위치</span><span class="sxs-lookup"><span data-stu-id="52021-122">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="52021-123">다음 코드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="52021-123">The following code provides an example:</span></span>  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="52021-124">Tlbimp를 사용 하 여 등록 되지 않은 COM 개체에 대해서도 형식 라이브러리에 대 한 interop 어셈블리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52021-124">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="52021-125">그러나 COM 개체에서 interop 어셈블리 참조 되는 데 사용할 컴퓨터에 제대로 등록 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52021-125">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="52021-126">Windows 운영 체제에 포함 된 Regsvr32 유틸리티를 사용 하 여 COM 개체를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52021-126">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52021-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52021-127">See Also</span></span>  
 [<span data-ttu-id="52021-128">COM Interop</span><span class="sxs-lookup"><span data-stu-id="52021-128">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 [<span data-ttu-id="52021-129">Tlbimp.exe(형식 라이브러리 가져오기)</span><span class="sxs-lookup"><span data-stu-id="52021-129">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [<span data-ttu-id="52021-130">Tlbexp.exe(형식 라이브러리 내보내기)</span><span class="sxs-lookup"><span data-stu-id="52021-130">Tlbexp.exe (Type Library Exporter)</span></span>](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [<span data-ttu-id="52021-131">연습: COM 개체를 사용한 상속 구현</span><span class="sxs-lookup"><span data-stu-id="52021-131">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [<span data-ttu-id="52021-132">상호 운용성 문제 해결</span><span class="sxs-lookup"><span data-stu-id="52021-132">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [<span data-ttu-id="52021-133">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="52021-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
