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
ms.openlocfilehash: 92327c8ff6232e64bf8b6b2a9d78e4a9eb30f3e1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="xamlname-grammar"></a><span data-ttu-id="70dd0-102">XamlName 문법</span><span class="sxs-lookup"><span data-stu-id="70dd0-102">XamlName Grammar</span></span>
<span data-ttu-id="70dd0-103">XamlName 문법에 편의 위해 여기에 재현 되어 XAML 언어 사양 [MS XAML], 정의 된 특정 문법입니다.</span><span class="sxs-lookup"><span data-stu-id="70dd0-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="70dd0-104">XAML 사양에서</span><span class="sxs-lookup"><span data-stu-id="70dd0-104">From the XAML Specification</span></span>  
 <span data-ttu-id="70dd0-105">[MS XAML] 사양은 유형 및 속성에 사용 되는 올바른 기호 식별자의 집합을 식별 하기 위해 XamlName 문법을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="70dd0-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="70dd0-106">문자열 값 형식인 XamlName 다음 문법을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70dd0-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="70dd0-107">유니코드 문자 데이터베이스에 정의 된 대로 다음과 같은 일반 범주 값을 가정 하</span><span class="sxs-lookup"><span data-stu-id="70dd0-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  
  
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
  
 <span data-ttu-id="70dd0-108">XAML DottedXamlName 속성에 사용 되는 두 번째 문법적으로 정의 하 고 이벤트 정규화 된 참조를 한도 대 한 멤버를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="70dd0-108">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="70dd0-109">자세한 내용은 참조 <xref:System.Windows.DependencyProperty> 및 [XAML 개요 (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70dd0-109">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).</span></span>  
  
 <span data-ttu-id="70dd0-110">문자열 값 형식인 DottedXamlName 다음 문법을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70dd0-110">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="70dd0-111">설명</span><span class="sxs-lookup"><span data-stu-id="70dd0-111">Remarks</span></span>  
 <span data-ttu-id="70dd0-112">완전 한 사양에 대 한 참조 [ \[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="70dd0-112">For the complete specification, see [\[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>
