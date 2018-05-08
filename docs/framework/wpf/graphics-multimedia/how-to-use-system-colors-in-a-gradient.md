---
title: '방법: 그라데이션에 시스템 색 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
ms.openlocfilehash: 4c3fca1db031b0dc397e9db58195b9714ff8aa9a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-system-colors-in-a-gradient"></a>방법: 그라데이션에 시스템 색 사용
그라데이션에서 시스템 색을 사용 하려면 사용는  *\<SystemColor >* 색 및  *\<SystemColor >* ColorKey의 정적 속성은 <xref:System.Windows.SystemColors> 얻으려고 클래스는 표시 되는 색에 대 한 참조를  *\<SystemColor >* 시스템 색의 이름입니다. 사용 하 여는  *\<SystemColor >* 자동 시스템 테마 변경 내용으로 업데이트 하는 동적 참조를 만들려는 ColorKey 속성입니다. 그렇지 않은 경우 사용 된  *\<SystemColor >* 색 속성입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 동적 시스템 색 리소스를 사용하여 그라데이션을 만듭니다.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 그 다음 예제에서는 정적 시스템 색 리소스를 사용하여 그라데이션을 만듭니다.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.SystemColors>  
 [시스템 브러시로 영역 그리기](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
