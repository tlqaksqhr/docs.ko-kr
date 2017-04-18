---
title: "방법: 입력 마스크 설정 | Microsoft Docs"
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
  - "net.ComponentModel.MaskPropertyEditor"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "MaskedTextBox 컨트롤[Windows Forms]"
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 입력 마스크 설정
마스킹된 텍스트 상자 컨트롤은 사용자 입력을 받아들이거나 거부하기 위한 선언적 구문을 지원하는 향상된 텍스트 상자 컨트롤입니다.  Mask 속성을 설정하면 응용 프로그램에 사용자 지정 유효성 검사 논리를 작성하지 않고도 허용 가능한 사용자 입력을 지정할 수 있습니다.  자세한 내용은 <xref:System.Windows.Forms.MaskedTextBox> 클래스의 설명 단원을 참조하십시오.  
  
## 수동으로 Mask 속성 설정  
 Mask 속성이 지원하는 문자를 잘 알고 있으면 수동으로 속성을 입력할 수 있습니다.  Mask 속성이 지원하는 문자에 대한 요약은 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성의 설명 부분을 참조하십시오.  
  
#### 수동으로 Mask 속성을 설정하려면  
  
1.  **디자인** 뷰에서 <xref:System.Windows.Forms.MaskedTextBox>를 선택합니다.  
  
2.  **속성** 창에서 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성을 찾습니다.  
  
3.  원하는 마스크\(예:  `###`\)를 입력합니다.  
  
## 입력 마스크 대화 상자 사용  
 입력 마스크 대화 상자에는 미리 정의된 몇 개의 입력 마스크가 있습니다.  미리 정의된 마스크를 변경하거나 사용자가 직접 마스크를 입력할 수도 있습니다.  
  
#### 입력 마스크 대화 상자를 열려면  
  
1.  **디자인** 뷰에서 <xref:System.Windows.Forms.MaskedTextBox>를 선택합니다.  
  
    1.  스마트 태그를 클릭하여 **MaskedTextBox 작업** 패널을 엽니다.  
  
    2.  **마스크 설정**을 클릭합니다.  
  
     \-또는\-  
  
    1.  **속성** 창에서 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성을 선택합니다.  
  
    2.  속성 값 열에 있는 줄임표 단추를 클릭합니다.  
  
     **입력 마스크** 대화 상자가 나타납니다.  
  
#### 입력 마스크 대화 상자를 사용하려면  
  
1.  \(선택 사항\) 목록에서 미리 정의된 마스크 중 하나를 클릭합니다.  
  
2.  \(선택 사항\) **마스크** 상자에서 미리 정의된 마스크를 편집합니다.  
  
3.  \(선택 사항\) **마스크** 상자에 새 마스크를 입력합니다.  즉, 미리 정의된 마스크 중 하나를 사용할 필요가 없습니다.  
  
    > [!NOTE]
    >  미리 보기 상자에는 <xref:System.Windows.Forms.MaskedTextBox>에서 사용자에게 표시되는 문자가 표시됩니다.  이러한 문자는 사용자가 데이터를 올바르게 입력하는 데 도움이 됩니다.  
  
4.  **ValidatingType 사용** 확인란을 선택하거나 선택 취소합니다.  **ValidatingType 사용** 확인란은 데이터 형식을 사용하여 사용자가 입력한 데이터를 확인할지 여부를 지정합니다.  자세한 내용은 <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 속성을 참조하십시오.  
  
5.  **확인**을 클릭합니다.  
  
     마스크가 **속성** 창의 **Mask** 속성에 입력됩니다.  
  
## 참고 항목  
 [연습: MaskedTextBox 컨트롤 사용](../../../../docs/framework/winforms/controls/walkthrough-working-with-the-maskedtextbox-control.md)