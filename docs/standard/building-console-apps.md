---
title: ".NET Framework에서 콘솔 응용 프로그램 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, building console applications
- application development [.NET Framework], console
- console applications
ms.assetid: c21fb997-9f0e-40a5-8741-f73bba376bd8
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4e0bc3f14a3d21776506f0a269a1a8c9f970cac0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="building-console-applications-in-the-net-framework"></a><span data-ttu-id="7c2f8-102">.NET Framework에서 콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="7c2f8-102">Building Console Applications in the .NET Framework</span></span>
<span data-ttu-id="7c2f8-103">.NET Framework의 응용 프로그램에서는 <xref:System.Console?displayProperty=nameWithType> 클래스를 사용하여 콘솔로부터 문자를 읽거나 콘솔에 문자를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2f8-103">Applications in the .NET Framework can use the <xref:System.Console?displayProperty=nameWithType> class to read characters from and write characters to the console.</span></span> <span data-ttu-id="7c2f8-104">콘솔의 데이터는 표준 입력 스트림에서 읽혀지고 표준 출력 스트림으로 쓰여지며, 콘솔의 오류 데이터는 표준 오류 출력 스트림으로 쓰여집니다.</span><span class="sxs-lookup"><span data-stu-id="7c2f8-104">Data from the console is read from the standard input stream, data to the console is written to the standard output stream, and error data to the console is written to the standard error output stream.</span></span> <span data-ttu-id="7c2f8-105">이러한 스트림은 응용 프로그램이 시작될 때 콘솔과 자동으로 연결되며 <xref:System.Console.In%2A>, <xref:System.Console.Out%2A> 및 <xref:System.Console.Error%2A> 속성으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="7c2f8-105">These streams are automatically associated with the console when the application starts and are presented as the <xref:System.Console.In%2A>, <xref:System.Console.Out%2A>, and <xref:System.Console.Error%2A> properties, respectively.</span></span>  
  
 <span data-ttu-id="7c2f8-106"><xref:System.Console.In%2A?displayProperty=nameWithType> 속성의 값은 <xref:System.IO.TextReader?displayProperty=nameWithType> 개체인 반면 <xref:System.Console.Out%2A?displayProperty=nameWithType> 및 <xref:System.Console.Error%2A?displayProperty=nameWithType> 속성의 값은 <xref:System.IO.TextWriter?displayProperty=nameWithType> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7c2f8-106">The value of the <xref:System.Console.In%2A?displayProperty=nameWithType> property is a <xref:System.IO.TextReader?displayProperty=nameWithType> object, whereas the values of the <xref:System.Console.Out%2A?displayProperty=nameWithType> and <xref:System.Console.Error%2A?displayProperty=nameWithType> properties are <xref:System.IO.TextWriter?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="7c2f8-107">콘솔을 나타내지 않는 스트림과 이들 속성을 연결하여 스트림이 서로 다른 입력 또는 출력 위치를 향하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2f8-107">You can associate these properties with streams that do not represent the console, making it possible for you to point the stream to a different location for input or output.</span></span> <span data-ttu-id="7c2f8-108">예를 들어 <xref:System.Console.Out%2A?displayProperty=nameWithType> 속성을 <xref:System.IO.StreamWriter?displayProperty=nameWithType>로 설정하여 출력을 파일로 리디렉션할 수 있습니다. 이 속성 값은 <xref:System.IO.FileStream?displayProperty=nameWithType>을 <xref:System.Console.SetOut%2A?displayProperty=nameWithType> 메서드로 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2f8-108">For example, you can redirect the output to a file by setting the <xref:System.Console.Out%2A?displayProperty=nameWithType> property to a <xref:System.IO.StreamWriter?displayProperty=nameWithType>, which encapsulates a <xref:System.IO.FileStream?displayProperty=nameWithType> by means of the <xref:System.Console.SetOut%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7c2f8-109"><xref:System.Console.In%2A?displayProperty=nameWithType> 및 <xref:System.Console.Out%2A?displayProperty=nameWithType> 속성은 동일한 스트림을 참조할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2f8-109">The <xref:System.Console.In%2A?displayProperty=nameWithType> and <xref:System.Console.Out%2A?displayProperty=nameWithType> properties do not need to refer to the same stream.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c2f8-110">C#, Visual Basic 및 C++의 예제를 비롯하여 콘솔 응용 프로그램을 빌드하는 방법에 대한 자세한 내용은 <xref:System.Console> 클래스 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c2f8-110">For more information about building console applications, including examples in C#, Visual Basic, and C++, see the documentation for the <xref:System.Console> class.</span></span>  
  
 <span data-ttu-id="7c2f8-111">Windows 기반 응용 프로그램 내에 콘솔이 존재하지 않을 경우 정보를 쓸 콘솔이 없으므로 표준 출력 스트림에 쓰여지는 출력은 보이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2f8-111">If the console does not exist, as in a Windows-based application, output written to the standard output stream will not be visible, because there is no console to write the information to.</span></span> <span data-ttu-id="7c2f8-112">액세스할 수 없는 콘솔에 정보를 쓸 경우 예외가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2f8-112">Writing information to an inaccessible console does not cause an exception to be raised.</span></span>  
  
 <span data-ttu-id="7c2f8-113">또는 Visual Studio를 사용하여 개발된 Windows 기반 응용 프로그램 내에서 콘솔의 읽기 및 쓰기를 설정하려면 프로젝트의 **속성** 대화 상자를 열고, **응용 프로그램** 탭을 클릭하고, **응용 프로그램 종류**를 **콘솔 응용 프로그램**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c2f8-113">Alternately, to enable the console for reading and writing within a Windows-based application that is developed using Visual Studio, open the project's **Properties** dialog box, click the **Application** tab, and set the **Application type** to **Console Application**.</span></span>  
  
 <span data-ttu-id="7c2f8-114">콘솔 응용 프로그램에는 기본적으로 시작되는 메시지 펌프가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2f8-114">Console applications lack a message pump that starts by default.</span></span> <span data-ttu-id="7c2f8-115">따라서 Microsoft Win32 타이머에 대한 콘솔 호출이 실패할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2f8-115">Therefore, console calls to Microsoft Win32 timers might fail.</span></span>  
  
 <span data-ttu-id="7c2f8-116">**System.Console** 클래스에는 콘솔에서 개별 문자나 전체 줄을 읽을 수 있는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c2f8-116">The **System.Console** class has methods that can read individual characters or entire lines from the console.</span></span> <span data-ttu-id="7c2f8-117">다른 메서드는 데이터 및 형식 문자열을 변환한 다음 형식 지정된 문자열을 콘솔에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="7c2f8-117">Other methods convert data and format strings, and then write the formatted strings to the console.</span></span> <span data-ttu-id="7c2f8-118">문자열 형식 지정에 대한 자세한 내용은 [형식 서식 지정](../../docs/standard/base-types/formatting-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c2f8-118">For more information on formatting strings, see [Formatting Types](../../docs/standard/base-types/formatting-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c2f8-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c2f8-119">See Also</span></span>  
 <xref:System.Console?displayProperty=nameWithType>  
 [<span data-ttu-id="7c2f8-120">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="7c2f8-120">Formatting Types</span></span>](../../docs/standard/base-types/formatting-types.md)
