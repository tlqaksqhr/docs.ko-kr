---
title: "방법: 관리되는 HTML 문서 개체 모델의 요소에 대한 스타일 변경 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "관리되는 HTML DOM, 요소에 대한 스타일 변경"
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 관리되는 HTML 문서 개체 모델의 요소에 대한 스타일 변경
HTML에 스타일을 사용하여 문서의 모양과 요소를 제어할 수 있습니다.  <xref:System.Windows.Forms.HtmlDocument> 및 <xref:System.Windows.Forms.HtmlElement>는 다음과 같은 형식의 스타일 문자열을 사용하는 <xref:System.Windows.Forms.HtmlElement.Style%2A> 속성을 지원합니다.  
  
 `name1:value1;...;nameN:valueN;`  
  
 다음 `DIV`에는 글꼴을 굴림으로 설정하고 모든 텍스트를 굵게 설정하는 스타일 문자열이 포함되어 있습니다.  
  
 `<DIV style="font-face:arial;font-weight:bold;">`  
  
 `Hello, world!`  
  
 `</DIV>`  
  
 <xref:System.Windows.Forms.HtmlElement.Style%2A> 속성을 사용하여 스타일을 조작하면 문자열에서 개별 스타일 설정을 제거하거나 추가하는 작업이 번거로울 수 있다는 것이 문제점입니다.  예를 들어, 사용자가 `DIV`에 커서를 가져갈 때마다 앞의 텍스트를 기울임꼴로 렌더링하고 커서가 `DIV`에서 벗어나면 기울임꼴이 해제되도록 하는 절차는 복잡합니다.  이런 방법을 사용하면 많은 스타일을 조작해야 하는 경우 시간이 오래 걸리는 문제가 있습니다.  
  
 다음 절차에 포함되어 있는 코드를 사용하면 HTML 문서와 요소에 대해 스타일을 쉽게 조작할 수 있습니다.  Windows Forms에서 새 프로젝트를 만들거나 컨트롤을 폼에 추가하는 등의 기본 작업을 수행하는 방법을 알고 있어야 이 절차를 수행할 수 있습니다.  
  
### Windows Forms 응용 프로그램에서 스타일을 변경하려면  
  
1.  새 Windows Forms 프로젝트를 만듭니다.  
  
2.  프로그래밍 언어에 적합한 확장명으로 끝나는 새 클래스 파일을 만듭니다.  
  
3.  이 항목의 예제 부분에 있는 `StyleGenerator` 클래스 코드를 클래스 파일에 복사하고 코드를 저장합니다.  
  
4.  다음 HTML을 Test.htm 파일로 저장합니다.  
  
    ```  
    <HTML>  
        <BODY>  
  
            <DIV style="font-face:arial;font-weight:bold;">  
                Hello, world!  
            </DIV><P>  
  
            <DIV>  
                Hello again, world!  
            </DIV><P>  
  
        </BODY>  
    </HTML>  
    ```  
  
5.  프로젝트의 기본 폼에 <xref:System.Windows.Forms.WebBrowser> 컨트롤인 `webBrowser1`을 추가합니다.  
  
6.  프로젝트의 코드 파일에 다음 코드를 추가합니다.  
  
    > [!IMPORTANT]
    >  `webBrowser1_DocumentCompleted` 이벤트 처리기가 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 이벤트의 수신기로 구성되어 있는지 확인합니다.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 <xref:System.Windows.Forms.WebBrowser> 컨트롤을 두 번 클릭하고 텍스트 편집기에서 수신기를 프로그래밍 방식으로 구성합니다.  
  
     [!code-csharp[ManagedDOMStyles#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]  
  
7.  프로젝트를 실행합니다.  첫 번째 `DIV`에서 커서를 실행하여 코드의 결과를 관찰합니다.  
  
## 예제  
 다음 코드 예제에서는 `StyleGenerator` 클래스의 전체 코드를 보여 줍니다. 이 클래스는 기존 스타일 값을 구문 분석하고 스타일의 추가, 변경 및 제거를 지원하며 요청한 변경 내용을 적용하여 새 스타일 값을 반환합니다.  
  
 [!code-csharp[ManagedDOMStyles#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
 [!code-vb[ManagedDOMStyles#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]  
  
## 참고 항목  
 <xref:System.Windows.Forms.HtmlElement>