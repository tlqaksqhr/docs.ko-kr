---
title: "방법: 사용자 지정 개체의 유효성 검사 논리 구현 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "유효성 검사 오류 확인[WPF]"
  - "사용자 지정 개체[WPF], 유효성 검사 논리 구현"
  - "사용자 지정 개체에 유효성 검사 논리 구현[WPF]"
  - "유효성 검사 오류[WPF], 확인"
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 사용자 지정 개체의 유효성 검사 논리 구현
이 예제에서는 사용자 지정 개체에서 유효성 검사 논리를 구현하고 바인딩하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서처럼 소스 개체에서 <xref:System.ComponentModel.IDataErrorInfo>를 구현하는 경우 비즈니스 계층에 유효성 검사 논리를 제공할 수 있습니다.  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 다음 예제에서 텍스트 상자의 텍스트 속성은 `x:Key` `data`가 지정된 리소스 선언을 통해 바인딩할 수 있게 된 `Person` 개체의 `Age` 속성에 바인딩됩니다.  <xref:System.Windows.Controls.DataErrorValidationRule>은 <xref:System.ComponentModel.IDataErrorInfo> 구현에서 발생하는 유효성 검사 오류를 검사합니다.  
  
 [!code-xml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml#boundtextbox)]  
  
 또는 <xref:System.Windows.Controls.DataErrorValidationRule>을 사용하는 대신 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 속성을 `true`로 설정할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Controls.ExceptionValidationRule>   
 [바인딩 유효성 검사 구현](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)