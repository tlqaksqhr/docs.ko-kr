---
title: "방법: 요소에서 표시기 제거"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 20d17ef43f99f6815334c0acbf7eb2040959751e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-remove-an-adorner-from-an-element"></a>방법: 요소에서 표시기 제거
프로그래밍 방식으로 지정 된 특정 표시기를 제거 하는 방법을 보여 주는이 예제 <xref:System.Windows.UIElement>합니다.  
  
## <a name="example"></a>예  
 반환 된 표시기의 배열에서 첫 번째 표시기를 제거 하는 자세한 코드 예제 <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>합니다.  이 예제에서는 발생에 표시기를 검색 하는 <xref:System.Windows.UIElement> 라는 *myTextBox*합니다.  요소에 대 한 호출에 지정 된 경우 <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> adorner가 없는, `null` 반환 됩니다.  이 코드는 명시적으로 null 배열을 확인 하 고는 null 배열 비교적 많이 필요한 응용 프로그램에 가장 적합 합니다.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a>예  
 이 압축 된 코드 예제에서는 위에 나와 있는 자세한 예제와 기능적으로 같습니다. 이 코드 검사 하지 않습니다 명시적으로 null 배열 수 있도록 하는 <xref:System.NullReferenceException> 예외가 발생할 수 있습니다.  이 코드는 많지 않은 null 배열이 필요한 응용 프로그램에 가장 적합 합니다.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a>참고 항목  
 [표시기 개요](../../../../docs/framework/wpf/controls/adorners-overview.md)
