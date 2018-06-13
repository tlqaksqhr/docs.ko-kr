---
title: '방법: 요소에서 모든 표시기 제거'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
ms.openlocfilehash: 5b7e2038c8a314a180ba097a30c124f874c25893
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551618"
---
# <a name="how-to-remove-all-adorners-from-an-element"></a>방법: 요소에서 모든 표시기 제거
프로그래밍 방식으로 지정 된 모든 표시기를 제거 하는 방법을 보여 주는이 예제 <xref:System.Windows.UIElement>합니다.  
  
## <a name="example"></a>예제  
 자세한 코드 예제에서는이 배열에서 반환 된 표시기에서 모든 표시기를 제거 <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>합니다.  이 예제에서는 발생에 표시기를 검색 하는 <xref:System.Windows.UIElement> 라는 *myTextBox*합니다.  요소에 대 한 호출에 지정 된 경우 <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> adorner가 없는, `null` 반환 됩니다.  이 코드는 명시적으로 null 배열을 확인 하 고는 null 배열 비교적 많이 필요한 응용 프로그램에 가장 적합 합니다.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a>예제  
 이 압축 된 코드 예제에서는 위에 나와 있는 자세한 예제와 기능적으로 같습니다. 이 코드 검사 하지 않습니다 명시적으로 null 배열 수 있도록 하는 <xref:System.NullReferenceException> 예외가 발생할 수 있습니다.  이 코드는 많지 않은 null 배열이 필요한 응용 프로그램에 가장 적합 합니다.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a>참고 항목  
 [표시기 개요](../../../../docs/framework/wpf/controls/adorners-overview.md)
