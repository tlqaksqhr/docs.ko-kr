---
title: "방법: Visual Basic에서 COM 개체 참조 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- COM interop, referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5f7f1112161d9be995cc80378ad9dd95c522198d
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="fbc8b-102">방법: Visual Basic에서 COM 개체 참조</span><span class="sxs-lookup"><span data-stu-id="fbc8b-102">How to: Reference COM Objects from Visual Basic</span></span>
<span data-ttu-id="fbc8b-103">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], COM 라이브러리에 대 한 interop 어셈블리의 생성이 필요한 형식 라이브러리가 있는 COM 개체에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="fbc8b-104">COM 개체의 멤버에 대 한 참조는 interop 어셈블리에 라우팅되고 실제 COM 개체에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="fbc8b-105">Interop 어셈블리를 COM 개체의 응답은 라우팅되고로 전달 하면 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-105">Responses from the COM object are routed to the interop assembly and forwarded to your [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] application.</span></span>  
  
 <span data-ttu-id="fbc8b-106">.NET 어셈블리에서 COM 개체에 대 한 형식 정보를 포함 하 여 interop 어셈블리를 사용 하지 않고 COM 개체를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="fbc8b-107">형식 정보를 포함 하려면 설정의 `Embed Interop Types` 속성을 `True` COM 개체에 대 한 참조에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="fbc8b-108">명령줄 컴파일러를 사용 하 여 컴파일하는 사용 하 여는 `/link` COM 라이브러리를 참조 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="fbc8b-109">자세한 내용은 참조 [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-109">For more information, see [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span></span>  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="fbc8b-110">통합된 개발 환경 (IDE)에서 형식 라이브러리에 대 한 참조를 추가 하면 interop 어셈블리를 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-110"> automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="fbc8b-111">명령줄에서 작업을 하는 경우 interop 어셈블리를 수동으로 만들려고 Tlbimp 유틸리티를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="fbc8b-112">COM 개체에 대 한 참조를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="fbc8b-112">To add references to COM objects</span></span>  
  
1.  <span data-ttu-id="fbc8b-113">에 **프로젝트** 메뉴 선택 **참조 추가** 클릭 하 고는 **COM** 대화 상자에서 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2.  <span data-ttu-id="fbc8b-114">COM 개체의 목록에서 사용 하려는 구성 요소를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3.  <span data-ttu-id="fbc8b-115">Interop 어셈블리에 대 한 액세스를 간단 하 게 하려면 추가 `Imports` 문을 클래스나 모듈을 사용 하 여 COM 개체의 맨 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="fbc8b-116">예를 들어, 다음 코드 예제에서는 네임 스페이스를 가져옵니다 `INKEDLib` 개체에서 참조 되는 `Microsoft InkEdit Control 1.0` 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     <span data-ttu-id="fbc8b-117">[!code-vb[VbVbalrInterop #&40;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="fbc8b-117">[!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]</span></span>  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="fbc8b-118">Tlbimp를 사용 하 여 interop 어셈블리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="fbc8b-118">To create an interop assembly using Tlbimp</span></span>  
  
1.  <span data-ttu-id="fbc8b-119">아직 없는 검색 경로의 일부를 모르면 현재 위치한 디렉터리의 경우에 검색 경로에 Tlbimp의 위치를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-119">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2.  <span data-ttu-id="fbc8b-120">다음 정보를 제공 하는 명령 프롬프트에서 Tlbimp를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-120">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    -   <span data-ttu-id="fbc8b-121">형식 라이브러리를 포함 하는 DLL의 이름 및 위치</span><span class="sxs-lookup"><span data-stu-id="fbc8b-121">Name and location of the DLL that contains the type library</span></span>  
  
    -   <span data-ttu-id="fbc8b-122">이름 및 네임 스페이스 정보를 배치할 위치</span><span class="sxs-lookup"><span data-stu-id="fbc8b-122">Name and location of the namespace where the information should be placed</span></span>  
  
    -   <span data-ttu-id="fbc8b-123">대상 interop 어셈블리의 이름 및 위치</span><span class="sxs-lookup"><span data-stu-id="fbc8b-123">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="fbc8b-124">다음 코드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-124">The following code provides an example:</span></span>  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="fbc8b-125">Tlbimp를 사용 하 여 등록 되지 않은 COM 개체에 대해서도 형식 라이브러리를 interop 어셈블리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-125">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="fbc8b-126">그러나 interop 어셈블리에서 참조 하는 COM 개체는 사용할 수는 컴퓨터에 제대로 등록 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-126">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="fbc8b-127">Windows 운영 체제에 포함 된 Regsvr32 유틸리티를 사용 하 여 COM 개체를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc8b-127">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbc8b-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fbc8b-128">See Also</span></span>  
 <span data-ttu-id="fbc8b-129">[COM Interop](../../../visual-basic/programming-guide/com-interop/index.md) </span><span class="sxs-lookup"><span data-stu-id="fbc8b-129">[COM Interop](../../../visual-basic/programming-guide/com-interop/index.md) </span></span>  
<span data-ttu-id="fbc8b-130"> [Tlbimp.exe (형식 라이브러리 가져오기)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) </span><span class="sxs-lookup"><span data-stu-id="fbc8b-130"> [Tlbimp.exe (Type Library Importer)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) </span></span>  
<span data-ttu-id="fbc8b-131"> [Tlbexp.exe (형식 라이브러리 내보내기)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d) </span><span class="sxs-lookup"><span data-stu-id="fbc8b-131"> [Tlbexp.exe (Type Library Exporter)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d) </span></span>  
<span data-ttu-id="fbc8b-132"> [연습: COM 개체를 사용한 상속 구현](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span><span class="sxs-lookup"><span data-stu-id="fbc8b-132"> [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span></span>  
<span data-ttu-id="fbc8b-133"> [상호 운용성 문제 해결](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md) </span><span class="sxs-lookup"><span data-stu-id="fbc8b-133"> [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md) </span></span>  
<span data-ttu-id="fbc8b-134"> [Imports 문(.NET 네임스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span><span class="sxs-lookup"><span data-stu-id="fbc8b-134"> [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span></span>
