---
title: "방법: Windows 응용 프로그램에서 도움말 제공 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "폼, 도움말 제공"
  - "도움말, Windows 응용 프로그램"
  - "HelpProvider 구성 요소[Windows Forms]"
  - "HTML 도움말, Windows Forms"
  - "Windows 응용 프로그램, 도움말 제공"
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: Windows 응용 프로그램에서 도움말 제공
<xref:System.Windows.Forms.HelpProvider> 구성 요소를 사용하여 도움말 파일 내의 도움말 항목을 Windows Forms의 특정 컨트롤에 연결할 수 있습니다.  도움말 파일은 HTML 또는 HTMLHelp 1.x 이상 형식일 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 도움말을 제공하려면  
  
1.  **도구 상자**에서 <xref:System.Windows.Forms.HelpProvider> 구성 요소를 사용자 폼으로 끌어 옵니다.  
  
     구성 요소가 Windows Forms 디자이너 아래에 있는 트레이에 배치됩니다.  
  
2.  **속성** 창에서 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 속성을 .chm, .col 또는 .htm 도움말 파일로 설정합니다.  
  
3.  폼에 있는 다른 컨트롤을 선택하여 **속성** 창에서 [HelpKeyword](frlrfSystemWindowsFormsHelpProviderClassSetHelpKeywordTopic) 속성을 설정합니다.  
  
     이것은 <xref:System.Windows.Forms.HelpProvider> 구성 요소를 통해 사용자의 도움말 파일에 전달되는 문자열로서 해당 도움말 항목을 호출합니다.  
  
4.  **속성** 창에서 [HelpNavigator](frlrfSystemWindowsFormsHelpProviderClassSetHelpNavigatorTopic) 속성을 <xref:System.Windows.Forms.HelpNavigator> 열거형 값으로 설정합니다.  
  
     이 값은 **HelpKeyword** 속성이 도움말 시스템에 전달되는 방식을 결정합니다.  다음 표에서는 가능한 설정과 해당 설명을 보여 줍니다.  
  
    |멤버 이름|설명|  
    |-----------|--------|  
    |AssociateIndex|지정한 항목에 대한 색인이 지정한 URL에서 수행되도록 지정합니다.|  
    |Find|지정한 URL의 검색 페이지를 표시하도록 지정합니다.|  
    |Index|지정한 URL의 색인을 표시하도록 지정합니다.|  
    |KeywordIndex|검색할 키워드 및 지정한 URL에서 수행할 작업을 지정합니다.|  
    |TableOfContents|HTML 1.0 도움말 파일의 목차를 표시하도록 지정합니다.|  
    |항목|지정한 URL에서 참조하는 항목을 표시하도록 지정합니다.|  
  
 런타임에 컨트롤\(**HelpKeyword** 및 **HelpNavigator** 속성을 설정한 컨트롤\)에 포커스가 있을 때 F1 키를 누르면 해당 <xref:System.Windows.Forms.HelpProvider> 구성 요소와 관련된 도움말 파일이 열립니다.  
  
 현재 **HelpNamespace** 속성은 HTMLHelp 1.x, HTMLHelp 2.0 및 HTML 형식의 도움말 파일을 지원합니다.  따라서 **HelpNamespace** 속성을 웹 페이지와 같은 http:\/\/ 주소로 설정할 수 있습니다.  이렇게 설정하면 앵커로 사용된 **HelpKeyword** 속성에 지정된 문자열이 있는 웹 페이지가 기본 브라우저에 열립니다.  앵커는 HTML 페이지에서 특정 부분으로 점프하기 위해 사용됩니다.  
  
> [!IMPORTANT]
>  클라이언트가 전송한 모든 정보는 응용 프로그램에서 사용하기 전에 반드시 검사해야 합니다.  악의적인 사용자가 실행 스크립트, SQL 문 또는 기타 코드를 전송 또는 주입할 수도 있습니다.  사용자 입력을 표시하거나, 데이터베이스에 저장하거나, 사용자 입력을 사용하여 작업하기 전에 잠재적으로 위험한 정보가 포함되어 있지 않은지 검사해야 합니다.  일반적인 검사 방법은 사용자 입력을 받을 때 정규식을 사용하여 "SCRIPT" 등의 키워드를 검색하는 것입니다.  
  
 비록 Windows Forms에서 컨트롤에 대한 도움말 파일이 표시되도록 구성했더라도 <xref:System.Windows.Forms.HelpProvider> 구성 요소를 사용하여 팝업 도움말을 표시할 수도 있습니다.  자세한 내용은 [방법: 팝업 도움말 표시](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)를 참조하십시오.  
  
## 참고 항목  
 [방법: 팝업 도움말 표시](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)   
 [ToolTip을 사용한 컨트롤 도움말](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)   
 [Windows Forms에 사용자 도움말 통합](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)