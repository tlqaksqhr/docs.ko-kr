---
title: "XamlName 문법"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
caps.latest.revision: "13"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47a2d72ea9558003412cc3773e26fb5be751fa19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="xamlname-grammar"></a>XamlName 문법
XamlName 문법에 편의 위해 여기에 재현 되어 XAML 언어 사양 [MS XAML], 정의 된 특정 문법입니다.  
  
## <a name="from-the-xaml-specification"></a>XAML 사양에서  
 [MS XAML] 사양은 유형 및 속성에 사용 되는 올바른 기호 식별자의 집합을 식별 하기 위해 XamlName 문법을 정의 합니다.  
  
 문자열 값 형식인 XamlName 다음 문법을 따라야 합니다.  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 유니코드 문자 데이터베이스에 정의 된 대로 다음과 같은 일반 범주 값을 가정 하  
  
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
  
 XAML DottedXamlName 속성에 사용 되는 두 번째 문법적으로 정의 하 고 이벤트 정규화 된 참조를 한도 대 한 멤버를 연결 합니다. 자세한 내용은 참조 <xref:System.Windows.DependencyProperty> 및 [XAML 개요 (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)합니다.  
  
 문자열 값 형식인 DottedXamlName 다음 문법을 따라야 합니다.  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>설명  
 완전 한 사양에 대 한 참조 [ \[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.
