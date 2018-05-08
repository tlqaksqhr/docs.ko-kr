---
title: '방법: 사용자 지정 개체의 유효성 검사 논리 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
ms.openlocfilehash: dbeddb5eb6996d5758717ddd2d4d5af0b6f57f3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a>방법: 사용자 지정 개체의 유효성 검사 논리 구현
이 예제에서는 사용자 지정 개체에서 유효성 검사 논리를 구현 하 여 바인딩하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 소스 개체가 구현 하는 경우 비즈니스 계층에 유효성 검사 논리를 제공할 수 있습니다 <xref:System.ComponentModel.IDataErrorInfo>다음 예제와 같이,:  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 다음 예에서는 입력란의 텍스트 속성에 바인딩됩니다는 `Age` 속성의는 `Person` 바인딩에 지정 된 리소스 선언을 통해 사용할 수 있는 개체는 `x:Key``data`합니다. <xref:System.Windows.Controls.DataErrorValidationRule> 에 의해 발생 하는 유효성 검사 오류에 대 한 검사는 <xref:System.ComponentModel.IDataErrorInfo> 구현 합니다.  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml#boundtextbox)]  
  
 사용 하는 대신 또는 <xref:System.Windows.Controls.DataErrorValidationRule>를 설정할 수 있습니다는 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 속성을 `true`합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.ExceptionValidationRule>  
 [바인딩 유효성 검사 구현](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
