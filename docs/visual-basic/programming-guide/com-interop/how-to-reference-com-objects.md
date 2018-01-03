---
title: "방법: Visual Basic에서 COM 개체 참조"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a8ac167b40688b1d1116f148d0d5fd6afdcaada8
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="f6d64-102">방법: Visual Basic에서 COM 개체 참조</span><span class="sxs-lookup"><span data-stu-id="f6d64-102">How to: Reference COM Objects from Visual Basic</span></span>
<span data-ttu-id="f6d64-103">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], COM 라이브러리에 대 한 interop 어셈블리의 생성이 필요한 형식 라이브러리에 있는 COM 개체에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-103">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="f6d64-104">COM 개체의 멤버에 대 한 참조는 interop 어셈블리를 라우팅되고 실제 COM 개체에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="f6d64-105">Interop 어셈블리를 COM 개체의 응답은 라우팅되고에 전달 하면 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-105">Responses from the COM object are routed to the interop assembly and forwarded to your [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] application.</span></span>  
  
 <span data-ttu-id="f6d64-106">.NET 어셈블리에서 COM 개체에 대 한 형식 정보를 포함 하 여 interop 어셈블리를 사용 하지 않고 COM 개체를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="f6d64-107">설정 유형 정보를 포함 하려면는 `Embed Interop Types` 속성을 `True` COM 개체에 대 한 참조에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="f6d64-108">명령줄 컴파일러를 사용 하 여 컴파일하는 사용 하 여는 `/link` COM 라이브러리를 참조 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="f6d64-109">자세한 내용은 참조 [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-109">For more information, see [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="f6d64-110">통합된 개발 환경 (IDE)에서 형식 라이브러리에 대 한 참조를 추가 하는 경우 interop 어셈블리를 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-110"> automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="f6d64-111">명령줄에서 작업을 하는 경우 interop 어셈블리를 수동으로 만들려고 Tlbimp 유틸리티를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="f6d64-112">COM 개체에 대 한 참조를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="f6d64-112">To add references to COM objects</span></span>  
  
1.  <span data-ttu-id="f6d64-113">에 **프로젝트** 메뉴 선택 **참조 추가** 클릭 하 고는 **COM** 대화 상자에서 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2.  <span data-ttu-id="f6d64-114">COM 개체의 목록에서 사용할 구성 요소를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3.  <span data-ttu-id="f6d64-115">Interop 어셈블리에 대 한 액세스를 간소화 하기 위해 추가 `Imports` 문을 클래스 또는 모듈을 사용 하 여 COM 개체의 맨 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="f6d64-116">예를 들어, 다음 코드 예제에서는 네임 스페이스를 가져옵니다 `INKEDLib` 에서 참조 되는 개체는 `Microsoft InkEdit Control 1.0` 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="f6d64-117">Tlbimp를 사용 하 여 interop 어셈블리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="f6d64-117">To create an interop assembly using Tlbimp</span></span>  
  
1.  <span data-ttu-id="f6d64-118">이 포함 되어 있지 않은 검색 경로에 경우에 거주 하지 않는 현재 위치한 디렉터리 검색 경로에 Tlbimp의 위치를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-118">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2.  <span data-ttu-id="f6d64-119">다음 정보를 제공 하는 명령 프롬프트에서 Tlbimp를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-119">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    -   <span data-ttu-id="f6d64-120">형식 라이브러리를 포함 하는 DLL의 이름 및 위치</span><span class="sxs-lookup"><span data-stu-id="f6d64-120">Name and location of the DLL that contains the type library</span></span>  
  
    -   <span data-ttu-id="f6d64-121">이름 및 정보를 배치할 네임 스페이스의 위치</span><span class="sxs-lookup"><span data-stu-id="f6d64-121">Name and location of the namespace where the information should be placed</span></span>  
  
    -   <span data-ttu-id="f6d64-122">대상 interop 어셈블리의 이름 및 위치</span><span class="sxs-lookup"><span data-stu-id="f6d64-122">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="f6d64-123">다음 코드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-123">The following code provides an example:</span></span>  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="f6d64-124">Tlbimp를 사용 하 여도 등록 되지 않은 COM 개체에 대 한 형식 라이브러리에 대 한 interop 어셈블리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-124">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="f6d64-125">그러나 COM 개체에서 interop 어셈블리 참조는 사용할 수는 컴퓨터에 제대로 등록 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-125">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="f6d64-126">Windows 운영 체제에 포함 된 Regsvr32 유틸리티를 사용 하 여 COM 개체를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d64-126">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6d64-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6d64-127">See Also</span></span>  
 [<span data-ttu-id="f6d64-128">COM Interop</span><span class="sxs-lookup"><span data-stu-id="f6d64-128">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 [<span data-ttu-id="f6d64-129">Tlbimp.exe(형식 라이브러리 가져오기)</span><span class="sxs-lookup"><span data-stu-id="f6d64-129">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [<span data-ttu-id="f6d64-130">Tlbexp.exe(형식 라이브러리 내보내기)</span><span class="sxs-lookup"><span data-stu-id="f6d64-130">Tlbexp.exe (Type Library Exporter)</span></span>](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [<span data-ttu-id="f6d64-131">연습: COM 개체를 사용한 상속 구현</span><span class="sxs-lookup"><span data-stu-id="f6d64-131">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [<span data-ttu-id="f6d64-132">상호 운용성 문제 해결</span><span class="sxs-lookup"><span data-stu-id="f6d64-132">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [<span data-ttu-id="f6d64-133">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="f6d64-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
