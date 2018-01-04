---
title: "방법: SystemParameters 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec333fbc30374ff6f8e2e7674ab332644ff7aad0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-systemparameters"></a>방법: SystemParameters 사용
이 예제에 액세스 하 고 속성을 사용 하는 방법을 보여 줍니다 <xref:System.Windows.SystemParameters> 스타일 하거나 단추를 사용자 지정 합니다.  
  
## <a name="example"></a>예  
 시스템 리소스는 시스템 설정과 일관된 시각적 효과를 만들 수 있도록 몇 가지 시스템 기반 설정을 리소스로 노출합니다. <xref:System.Windows.SystemParameters>시스템 매개 변수 값 속성 및 값에 바인딩되는 시스템 리소스 키를 모두 포함 하는 클래스가입니다. 예를 들어 <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> 는 <xref:System.Windows.SystemParameters> 속성 값 및 <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> 해당 리소스 키입니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 멤버를 사용할 수 <xref:System.Windows.SystemParameters> 는 정적 속성 사용 또는 동적 리소스 참조 (정적 속성 값을 키로). 응용 프로그램이 실행되는 동안 시스템 기반 값을 자동으로 업데이트하려면 동적 리소스 참조를 사용하고 자동으로 업데이트하지 않으려면 정적 참조를 사용합니다. 리소스 키 접미사가 `Key` 속성 이름에 추가 합니다.  
  
 다음 예제에서는 액세스 하 고 정적 값을 사용 하는 방법을 보여 줍니다 <xref:System.Windows.SystemParameters> 에 스타일을 하거나 단추를 사용자 지정 합니다. 이 태그 예제 적용 하 여 단추의 크기 <xref:System.Windows.SystemParameters> 를 단추에는 값입니다.  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 값을 사용 하려면 <xref:System.Windows.SystemParameters> 코드에서 않아도 정적 참조 또는 동적 리소스 참조를 사용 하도록 합니다. 값을 사용 하는 대신는 <xref:System.Windows.SystemParameters> 클래스입니다. 키가 아닌 속성이 분명히 정적 속성의 런타임 동작으로 정의 된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시스템에서 호스팅될 때 실시간으로 속성을 다시 평가 하 고 적절 하 게 시스템 값을 사용자가 수행한 변경 작업에 대 한 고려 됩니다. 다음 예제를 사용 하 여 단추의 높이 너비를 설정 하는 방법을 보여 줍니다 <xref:System.Windows.SystemParameters> 값입니다.  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.SystemParameters>  
 [시스템 브러시로 영역 그리기](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [SystemFonts 사용](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [시스템 매개 변수 키 사용](../../../../docs/framework/wpf/advanced/how-to-use-system-parameters-keys.md)  
 [방법 항목](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
