---
title: "XamlName 문법 | Microsoft Docs"
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
  - "DottedXamlName 문법[XAML 서비스]"
  - "문법[XAML 서비스], DottedXamlName"
  - "문법[XAML 서비스], XamlName"
  - "XAML의 이름[XAML 서비스]"
  - "XamlName 문법[XAML 서비스]"
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
caps.latest.revision: 13
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 13
---
# XamlName 문법
XamlName 문법은 편의를 위해 여기에 재현된 XAML 언어 사양\[MS\-XAML\]에 정의된 특정 문법입니다.  
  
## XAML 사양  
 \[MS\-XAML\] 사양은 형식 및 속성에 사용되는 올바른 기호 식별자 집합을 식별하기 위해 XamlName 문법을 정의합니다.  
  
 XamlName 형식의 문자열 값은 다음 문법을 따라야 합니다.  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
  
```  
  
 이 문법은 유니코드 문자 데이터베이스에 정의된 다음과 같은 일반 범주 값을 사용합니다.  
  
```  
  
Lu  
Letter, Uppercase  
Ll  
Letter, Lowercase  
Lt  
Letter, Titlecase  
Lm  
Letter, Modifier  
Lo  
Letter, Other  
Mn  
Mark, Non-Spacing  
Mc  
Mark, Spacing Combining  
Nd  
Number, Decimal  
Nl  
Number, Letter  
```  
  
 XAML은 속성 및 이벤트 한정 참조에 사용되는 DottedXamlName이라는 두 번째 문법도 정의합니다. 이 문법은 연결된 멤버에도 사용됩니다.  자세한 내용은 <xref:System.Windows.DependencyProperty> 및 [XAML 개요\(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)를 참조하십시오.  
  
 DottedXamlName 형식의 문자열 값은 다음 문법을 따라야 합니다.  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## 설명  
 전체 사양은 [\[MS\-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525)을 참조하십시오.