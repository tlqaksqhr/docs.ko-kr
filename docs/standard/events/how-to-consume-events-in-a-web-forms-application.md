---
title: "방법: Web Forms 응용 프로그램에서 이벤트 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "이벤트[.NET Framework], Web Forms"
  - "Web Forms 컨트롤, 이벤트"
  - "이벤트 처리기[.NET Framework], Web Forms"
  - "이벤트[.NET Framework], 사용"
  - "Web Forms, 이벤트 처리"
ms.assetid: 73bf8638-c4ec-4069-b0bb-a1dc79b92e32
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# 방법: Web Forms 응용 프로그램에서 이벤트 사용
ASP.NET Web Forms 응용 프로그램의 주된 활용 방식은 웹 페이지에 컨트롤을 채운 다음 사용자가 클릭하는 컨트롤에 따라 특정 작업을 수행하는 것입니다.  예를 들어, <xref:System.Web.UI.WebControls.Button?displayProperty=fullName> 컨트롤은 사용자가 웹 페이지에서 해당 컨트롤을 클릭하면 이벤트를 발생시킵니다.  응용 프로그램은 이 이벤트를 처리하여 단추 클릭에 해당하는 적절한 응용 프로그램 논리를 수행할 수 있습니다.  
  
### 웹 페이지에서 단추 클릭 이벤트를 처리하려면  
  
1.  <xref:System.Web.UI.WebControls.Button> 컨트롤을 다음 단계에서 정의 하는 메서드의 이름으로 설정하는 `OnClick` 값과 함께 갖는 ASP.NET Web Forms 페이지 \(웹 페이지\)를 생성 합니다.  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2.  일치 하는 이벤트 처리기를 정의 <xref:System.Web.UI.WebControls.Button.Click> 이벤트 대리자 서명과 일치하고 `OnClick` 값으로 정의한 이름을 갖는 이벤트 처리기를 정의합니다.  
  
    ```csharp  
    protected void Button1_Click(object sender, EventArgs e)  
    {  
        // perform action  
    }  
    ```  
  
    ```vb  
    Protected Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' perform action  
    End Sub  
    ```  
  
     <xref:System.Web.UI.WebControls.Button.Click> 이벤트는 대리자 형식에 <xref:System.EventHandler> 클래스를 사용하고 이벤트 데이터에 <xref:System.EventArgs> 클래스를 사용합니다.  ASP.NET 페이지 프레임워크는 자동으로<xref:System.EventHandler> 의 인스턴스를 만들고  <xref:System.Web.UI.WebControls.Button> 인스턴스의 <xref:System.Web.UI.WebControls.Button.Click> 이벤트의 대리자 인스턴스를 추가합니다.  
  
3.  2단계에서 정의한 이벤트 처리기에서, 이벤트가 발생할 때 요구된 모든 작업을 수행하는 코드를 추가 합니다.  
  
## 참고 항목  
 [이벤트](../../../docs/standard/events/index.md)