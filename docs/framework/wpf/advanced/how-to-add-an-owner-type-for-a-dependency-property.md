---
title: '방법: 종속성 속성의 소유자 형식 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
ms.openlocfilehash: bf3f73743d1c76145bf520ed859c27c4d3aaf662
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542778"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a>방법: 종속성 속성의 소유자 형식 추가
이 예제는 클래스를 다른 형식에 대해 등록 된 종속성 속성의 소유자로 추가 하는 방법을 보여 줍니다. 이 수행 하 여는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 판독기 및 속성 시스템은 모두 속성의 소유자로 추가 클래스를 인식할 수 있습니다. 필요에 따라 소유자로 추가 추가 하는 클래스 형식별 메타 데이터를 제공할 수 있습니다.  
  
 다음 예에서 `StateProperty` 하 여 등록 하는 속성은 `MyStateControl` 클래스입니다. 클래스 `UnrelatedStateControl` 자체의 소유자로 추가 `StateProperty` 를 사용 하는 <xref:System.Windows.DependencyProperty.AddOwner%2A> 메서드를 추가 하는 형식에 있는 종속성 속성에 대 한 새 메타 데이터에 대 한 허용 하는 시그니처를 사용 하 여 합니다. 제공 해야 하는 알림 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 에 표시 된 예제와 비슷한 속성에 대 한 접근자는 [종속성 속성을 구현](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) 등으로 다시 추가 하는 클래스에서 종속성 속성 식별자를 노출 소유자입니다.  
  
 래퍼에 없는 종속성 속성에도 작동 사용 하 여 프로그래밍 방식 액세스의 관점에서 <xref:System.Windows.DependencyObject.GetValue%2A> 또는 <xref:System.Windows.DependencyObject.SetValue%2A>합니다. 하지만 일반적으로이 속성 시스템 동작은와 하려는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성 래퍼 합니다. 래퍼 더 쉽게 종속성 속성을 프로그래밍 방식으로 설정 하 고로 속성을 설정할 수 있게 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 특성입니다.  
  
 기본 메타 데이터를 재정의 하는 방법을 알아보려면 참조 [종속성 속성에 대 한 메타 데이터 재정의](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md)합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
