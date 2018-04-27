---
title: '방법: Windows Forms BindingSource를 사용하여 웹 서비스에 바인딩'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fbbdc57eeebef9c9f14610255ece799c1e8867e1
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource"></a>방법: Windows Forms BindingSource를 사용하여 웹 서비스에 바인딩
XML Web services 호출에서 얻은 결과에 Windows Form 컨트롤을 바인딩하려면 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하면 됩니다. 이 절차는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 형식에 바인딩하는 것과 비슷합니다. 웹 서비스에 의해 노출되는 메서드와 형식이 포함된 클라이언트 측 프록시를 만들어야 합니다. 웹 서비스(.asmx) 자체 또는 WSDL(Web Services Description Language) 파일에서 클라이언트 측 프록시를 생성합니다. 또한 클라이언트 측 프록시는 웹 서비스에서 공용 속성으로 사용되는 복합 형식의 필드를 노출해야 합니다. 그리고 나서 <xref:System.Windows.Forms.BindingSource>를 웹 서비스 프록시에 노출된 형식의 하나에 바인딩합니다.  
  
### <a name="to-create-and-bind-to-a-client-side-proxy"></a>클라이언트 측 프록시를 만들고 바인딩하려면 다음을 수행합니다.  
  
1.  적절한 네임스페이스를 사용하여 선택한 디렉터리에서 Windows Form을 만듭니다.  
  
2.  폼에 <xref:System.Windows.Forms.BindingSource> 구성 요소를 추가합니다.  
  
3.  [!INCLUDE[winsdklong](../../../../includes/winsdklong-md.md)] 명령 프롬프트를 열고 폼이 있는 같은 디렉터리로 이동합니다.  
  
4.  WSDL 도구를 사용하여 `wsdl`, 웹 서비스에 대한 .asmx 또는 WSDL 파일의 URL, 응용 프로그램의 네임스페이스를 차례로 입력하고 선택적으로 사용 중인 언어를 입력합니다.  
  
     다음 코드 예제에 있는 웹 서비스를 사용 하 여 http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx합니다. 예를 들어 C# 유형 `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService` 또는 Visual Basic 유형 `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`의 경우입니다. WSDL 도구에 경로를 인수로 전달하면 지정된 언어로 응용 프로그램과 같은 디렉터리 및 네임스페이스에 클라이언트 측 프록시가 생성됩니다. Visual Studio를 사용 하는 경우 파일을 프로젝트에 추가 합니다.  
  
5.  바인딩할 클라이언트 측 프록시의 형식을 선택합니다.  
  
     이는 일반적으로 웹 서비스에서 제공된 메서드가 반환한 형식입니다. 선택된 형식의 필드는 바인딩용 공용 속성으로 노출되어야 합니다.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#4)]  
  
6.  <xref:System.Windows.Forms.BindingSource>의 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 속성을 웹 서비스 클라이언트 측 프록시에 포함된 원하는 형식으로 설정합니다.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#2)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#2)]  
  
### <a name="to-bind-controls-to-the-bindingsource-that-is-bound-to-a-web-service"></a>웹 서비스에 바인딩된 BindingSource에 컨트롤을 바인딩하려면 다음을 수행합니다.  
  
-   컨트롤을 <xref:System.Windows.Forms.BindingSource>에 바인딩하여 원하는 웹 서비스 형식의 공용 속성을 매개 변수로 전달합니다.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#3)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#3)]  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 웹 서비스에 바인딩하는 방법과 텍스트 상자를 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩하는 방법을 차례로 보여 줍니다. 단추를 클릭할 때 웹 서비스 메서드가 호출되고 결과가 `textbox1`에 표시됩니다.  
  
 [!code-cpp[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 전체 예제에는 `Main` 메서드와 클라이언트 측 프록시 코드의 간략 버전이 포함됩니다.  
  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Drawing, System.Web.Services, System.Windows.Forms 및 System.Xml 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [방법: 형식에 Windows Forms 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
