---
title: "ErrorProvider 구성 요소 개요(Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ErrorProvider"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "오류 메시지, 표시"
  - "ErrorProvider 구성 요소[Windows Forms], ErrorProvider 구성 요소 정보"
  - "오류[Windows Forms], 사용자에게 표시"
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# ErrorProvider 구성 요소 개요(Windows Forms)
Windows Forms [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) 구성 요소는 사용자가 폼이나 컨트롤에 입력한 내용의 유효성을 검사하는 데 사용됩니다.  일반적으로 이 구성 요소는 폼에 대한 사용자 입력의 유효성을 검사하거나 데이터 집합의 오류를 표시하는 데 사용됩니다.  메시지 상자에 오류 메시지를 표시하는 경우에는 메시지 상자가 사라지고 나면 오류 메시지를 더 이상 볼 수 없기 때문에 오류 공급자를 사용하는 것이 더 좋은 방법일 수 있습니다.  <xref:System.Windows.Forms.ErrorProvider> 구성 요소는 텍스트 상자와 같은 관련 컨트롤 옆에 오류 아이콘\(![ErrorProvider 아이콘](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.png "vbErrorProviderIcon")\)을 표시합니다. 예를 들어, 사용자가 마우스 포인터를 오류 아이콘 위로 가져가면 도구 설명이 나타나고 오류 메시지 문자열이 표시됩니다.  
  
## 키 속성  
 <xref:System.Windows.Forms.ErrorProvider> 구성 요소의 주요 속성은 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 및 <xref:System.Windows.Forms.ErrorProvider.Icon%2A>입니다.  데이터 바인딩된 컨트롤과 함께 <xref:System.Windows.Forms.ErrorProvider> 구성 요소를 사용하는 경우 해당 구성 요소에서 폼에 오류 아이콘을 표시하도록 하려면 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 속성을 적절한 컨테이너\(보통 Windows Form\)로 설정해야 합니다.  디자이너에서 구성 요소를 추가하면 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 속성이 해당 구성 요소를 포함하는 폼으로 설정됩니다. 그러나 코드로 컨트롤을 추가하는 경우에는 이를 직접 설정해야 합니다.  
  
 <xref:System.Windows.Forms.ErrorProvider.Icon%2A> 속성은 기본값 대신 사용자 지정 오류 아이콘으로 설정할 수 있습니다.  <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> 속성을 설정하면 <xref:System.Windows.Forms.ErrorProvider> 구성 요소에서 데이터 집합에 대한 오류 메시지를 표시할 수 있습니다.  <xref:System.Windows.Forms.ErrorProvider> 구성 요소의 주요 메서드는 오류 메시지 문자열과 오류 아이콘의 표시 위치를 지정하는 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 메서드입니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ErrorProvider> 구성 요소는 기본적으로 액세스 가능 클라이언트를 지원하지 않습니다.  이 구성 요소를 사용할 때 응용 프로그램에 액세스 가능 기능을 제공하려면 액세스 가능 피드백 메커니즘을 추가로 제공해야 합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ErrorProvider>   
 [방법: Windows Forms ErrorProvider 구성 요소를 사용하여 데이터 집합에 있는 오류 보기](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)   
 [방법: Windows Forms ErrorProvider 구성 요소를 사용하여 폼 유효성에 대한 오류 아이콘 표시](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)