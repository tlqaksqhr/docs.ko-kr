---
title: "ImeMode 속성을 사용하여 전자 단어 표시 | Microsoft Docs"
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
  - "아시아 언어"
  - "아시아 언어, ImeMode로 표시"
  - "중국어 문자, ImeMode로 표시"
  - "전역화[Windows Forms], 문자 집합"
  - "IME 모드"
  - "IMEMode 속성"
  - "IME(입력기), 모드"
  - "국가별 응용 프로그램[Windows Forms], 문자 표시"
  - "국가별 문자"
  - "일본어 문자, ImeMode로 표시"
  - "한국어 문자"
  - "지역화[Windows Forms], 문자 집합"
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# ImeMode 속성을 사용하여 전자 단어 표시
<xref:System.Windows.Forms.Control.ImeMode%2A> 속성은 IME\(입력기\)를 특정 모드로 전환하기 위해 폼과 컨트롤에서 사용합니다.  입력기는 일반 키보드로 인코딩할 수 있는 것보다 더 많은 문자를 포함하고 있으므로 중국어, 일본어 및 한국어 스크립트를 작성하는 데 필수적인 구성 요소입니다.  예를 들어, 특정 입력란에 ASCII 문자만 사용하게 할 수도 있습니다.  이런 경우 특정 텍스트 상자의 <xref:System.Windows.Forms.Control.ImeMode%2A> 속성을 <xref:System.Windows.Forms.ImeMode>로 설정하면 사용자는 해당 텍스트 상자에 ASCII 문자만 입력할 수 있습니다.  <xref:System.Windows.Forms.Control.ImeMode%2A> 속성의 기본값이 <xref:System.Windows.Forms.ImeMode>이므로 폼에 대해 이 속성을 설정하면 폼에 있는 모든 컨트롤에 해당 설정이 상속됩니다.  자세한 내용은 [Control.ImeMode 속성](frlrfSystemWindowsFormsControlClassImeModeTopic) 및 [ImeMode 열거형](frlrfSystemWindowsFormsImeModeClassTopic)을 참조하십시오.  
  
## 참고 항목  
 [Windows Forms 전역화](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)