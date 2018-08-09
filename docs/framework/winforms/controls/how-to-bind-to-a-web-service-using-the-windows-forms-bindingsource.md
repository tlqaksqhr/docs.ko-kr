---
title: '방법: Windows Forms BindingSource를 사용하여 웹 서비스에 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Web services [Windows Forms], binding controls
- BindingSource component [Windows Forms], binding to a Web service
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to Web service
- BindingSource component [Windows Forms], examples
ms.assetid: ee261207-4573-4cb9-a8cb-5185037e0fba
ms.openlocfilehash: 5a5db651b0690aae393666124c8d33402d57a189
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531402"
---
# <a name="how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource"></a><span data-ttu-id="42dc6-102">방법: Windows Forms BindingSource를 사용하여 웹 서비스에 바인딩</span><span class="sxs-lookup"><span data-stu-id="42dc6-102">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>
<span data-ttu-id="42dc6-103">XML Web services 호출에서 얻은 결과에 Windows Form 컨트롤을 바인딩하려면 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-103">If you want to bind a Windows Form control to the results obtained from calling an XML Web service, you can use a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="42dc6-104">이 절차는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 형식에 바인딩하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-104">This procedure is similar to binding a <xref:System.Windows.Forms.BindingSource> component to a type.</span></span> <span data-ttu-id="42dc6-105">웹 서비스에 의해 노출되는 메서드와 형식이 포함된 클라이언트 측 프록시를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-105">You must create a client-side proxy that contains the methods and types exposed by the Web service.</span></span> <span data-ttu-id="42dc6-106">웹 서비스(.asmx) 자체 또는 WSDL(Web Services Description Language) 파일에서 클라이언트 측 프록시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-106">You generate a client-side proxy from the Web service (.asmx) itself, or its Web Services Description Language (WSDL) file.</span></span> <span data-ttu-id="42dc6-107">또한 클라이언트 측 프록시는 웹 서비스에서 공용 속성으로 사용되는 복합 형식의 필드를 노출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-107">Additionally, your client-side proxy must expose the fields of complex types used by the Web service as public properties.</span></span> <span data-ttu-id="42dc6-108">그리고 나서 <xref:System.Windows.Forms.BindingSource>를 웹 서비스 프록시에 노출된 형식의 하나에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-108">You then bind the <xref:System.Windows.Forms.BindingSource> to one of the types exposed in the Web service proxy.</span></span>  
  
### <a name="to-create-and-bind-to-a-client-side-proxy"></a><span data-ttu-id="42dc6-109">클라이언트 측 프록시를 만들고 바인딩하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-109">To create and bind to a client-side proxy</span></span>  
  
1.  <span data-ttu-id="42dc6-110">적절한 네임스페이스를 사용하여 선택한 디렉터리에서 Windows Form을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-110">Create a Windows Form in the directory of your choice, with an appropriate namespace.</span></span>  
  
2.  <span data-ttu-id="42dc6-111">폼에 <xref:System.Windows.Forms.BindingSource> 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-111">Add a <xref:System.Windows.Forms.BindingSource> component to the form.</span></span>  
  
3.  <span data-ttu-id="42dc6-112">[!INCLUDE[winsdklong](../../../../includes/winsdklong-md.md)] 명령 프롬프트를 열고 폼이 있는 같은 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-112">Open the [!INCLUDE[winsdklong](../../../../includes/winsdklong-md.md)] command prompt, and navigate to the same directory that your form is located in.</span></span>  
  
4.  <span data-ttu-id="42dc6-113">WSDL 도구를 사용하여 `wsdl`, 웹 서비스에 대한 .asmx 또는 WSDL 파일의 URL, 응용 프로그램의 네임스페이스를 차례로 입력하고 선택적으로 사용 중인 언어를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-113">Using the WSDL tool, enter `wsdl` and the URL for the .asmx or WSDL file for the Web service, followed by the namespace of your application, and optionally the language you are working in.</span></span>  
  
     <span data-ttu-id="42dc6-114">다음 코드 예제에 있는 웹 서비스를 사용 하 여 http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-114">The following code example uses the Web service located at http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx.</span></span> <span data-ttu-id="42dc6-115">예를 들어 C# 유형 `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService` 또는 Visual Basic 유형 `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`의 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-115">For example, for C# type `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService`, or for Visual Basic type `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`.</span></span> <span data-ttu-id="42dc6-116">WSDL 도구에 경로를 인수로 전달하면 지정된 언어로 응용 프로그램과 같은 디렉터리 및 네임스페이스에 클라이언트 측 프록시가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-116">Passing the path as an argument to the WSDL tool will generate a client-side proxy in the same directory and namespace as your application, in the specified language.</span></span> <span data-ttu-id="42dc6-117">Visual Studio를 사용 하는 경우 파일을 프로젝트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-117">If you are using Visual Studio, add the file to your project.</span></span>  
  
5.  <span data-ttu-id="42dc6-118">바인딩할 클라이언트 측 프록시의 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-118">Select a type in the client-side proxy to bind to.</span></span>  
  
     <span data-ttu-id="42dc6-119">이는 일반적으로 웹 서비스에서 제공된 메서드가 반환한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-119">This is typically a type returned by a method offered by the Web service.</span></span> <span data-ttu-id="42dc6-120">선택된 형식의 필드는 바인딩용 공용 속성으로 노출되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-120">The fields of the chosen type must be exposed as public properties for binding purposes.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#4)]  
  
6.  <span data-ttu-id="42dc6-121"><xref:System.Windows.Forms.BindingSource>의 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 속성을 웹 서비스 클라이언트 측 프록시에 포함된 원하는 형식으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-121">Set the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property of the <xref:System.Windows.Forms.BindingSource> to the type you want that is contained in the Web service client-side proxy.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#2)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#2)]  
  
### <a name="to-bind-controls-to-the-bindingsource-that-is-bound-to-a-web-service"></a><span data-ttu-id="42dc6-122">웹 서비스에 바인딩된 BindingSource에 컨트롤을 바인딩하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-122">To bind controls to the BindingSource that is bound to a Web service</span></span>  
  
-   <span data-ttu-id="42dc6-123">컨트롤을 <xref:System.Windows.Forms.BindingSource>에 바인딩하여 원하는 웹 서비스 형식의 공용 속성을 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-123">Bind controls to the <xref:System.Windows.Forms.BindingSource>, passing the public property of the Web service type that you want as a parameter.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#3)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="42dc6-124">예제</span><span class="sxs-lookup"><span data-stu-id="42dc6-124">Example</span></span>  
 <span data-ttu-id="42dc6-125">다음 코드 예제에서는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 웹 서비스에 바인딩하는 방법과 텍스트 상자를 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩하는 방법을 차례로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-125">The following code example demonstrates how to bind a <xref:System.Windows.Forms.BindingSource> component to a Web service, and then how to bind a text box to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="42dc6-126">단추를 클릭할 때 웹 서비스 메서드가 호출되고 결과가 `textbox1`에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-126">When you click the button, a Web service method is called and the results will appear in `textbox1`.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="42dc6-127">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="42dc6-127">Compiling the Code</span></span>  
 <span data-ttu-id="42dc6-128">이 전체 예제에는 `Main` 메서드와 클라이언트 측 프록시 코드의 간략 버전이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-128">This is a complete example that includes a `Main` method, and a shortened version of client-side proxy code.</span></span>  
  
 <span data-ttu-id="42dc6-129">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-129">This example requires:</span></span>  
  
-   <span data-ttu-id="42dc6-130">System, System.Drawing, System.Web.Services, System.Windows.Forms 및 System.Xml 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="42dc6-130">References to the System, System.Drawing, System.Web.Services, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="42dc6-131">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-131">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="42dc6-132">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42dc6-132">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="42dc6-133">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42dc6-133">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42dc6-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42dc6-134">See Also</span></span>  
 [<span data-ttu-id="42dc6-135">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="42dc6-135">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="42dc6-136">방법: 형식에 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="42dc6-136">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
