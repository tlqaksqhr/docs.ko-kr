---
title: x:Uid 지시문
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 667b722097d091902cb65f2e6f0485a039f8a2ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="xuid-directive"></a>x:Uid 지시문
태그 요소에 대 한 고유 식별자를 제공 합니다. 대부분의 경우에이 고유 식별자는 XAML 지역화 프로세스와 도구에서 사용 됩니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xaml  
<object x:Uid="identifier"... />  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`identifier`|수동으로 또는 자동으로 생성 된 문자열에 의해 해석 되는 경우 파일에서 고유 해야 하는 `x:Uid` 소비자입니다.|  
  
## <a name="remarks"></a>설명  
 [MS XAML]에서 `x:Uid` 지시문으로 정의 됩니다. 자세한 내용은 참조 [ \[MS-XAML\] 섹션 5.3.6](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.  
  
 `x:Uid` 불연속 `x:Name` 명시 XAML 지역화 시나리오 때문에 둘 다 고 지역화 하는 데 사용 되는 식별자의 프로그래밍 모델 의미 없는 종속성이 있는 `x:Name`합니다. 하지만 또한 `x:Name` XAML 이름 범위;에 의해 관리 `x:Uid` XAML 정의 된 언어 개념이 고유성 적용을 받지 않는 합니다. 광범위 한 의미는 (지역화 과정의 일부가 아닌 프로세서)에서 XAML 프로세서의 고유성을 강제 적용 되지 않을 `x:Uid` 값입니다. 이러한 일 값의 작성기 개념적으로 켜져 있습니다. 고유성을 기대 `x:Uid` 단일 XAML 소스 내에서 값은 부적절 한 전용된 전역화 프로세스 또는 도구와 같은 값의 소비자입니다. 일반적인 고유성 모델은 `x:Uid` 값이 XAML을 나타내는 XML로 인코딩된 파일 내에서 고유 합니다.  
  
 특정 XAML 스키마의 많은 기술 자료를 적용 하도록 선택할 수 `x:Uid` 에 대해서만 텍스트 문자열 값에 태그에서 발생 한 모든 경우에 대 한 지역화 가능한 문자열 대신 true입니다.  
  
 프레임 워크에 대 한 별칭 개체 모델에서 특정 속성을 지정할 수 `x:Uid` 특성을 적용 하 여 <xref:System.Windows.Markup.UidPropertyAttribute> 정의 형식에 있습니다. 프레임 워크는 특정 속성을 지정 하면 유효 하지 않은 모두 지정할 수 `x:Uid` 와 같은 개체에 별칭이 지정 된 멤버입니다. 두 `x:Uid` 및 별칭이 지정 된 멤버 지정 되며,.NET Framework XAML 서비스 API는 일반적으로 throw <xref:System.Xaml.XamlDuplicateMemberException> 이 있는 경우.  
  
## <a name="wpf-usage-notes"></a>WPF 사용 정보  
 역할에 대 한 자세한 내용은 `x:Uid` WPF 지역화 과정 및 BAML 형식의 XAML 참조 [WPF의 전역화](../../../docs/framework/wpf/advanced/globalization-for-wpf.md) 또는 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
 <xref:Microsoft.Build.Tasks.Windows.UidManager>  
 [WPF의 전역화](../../../docs/framework/wpf/advanced/globalization-for-wpf.md)
