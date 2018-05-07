---
title: x:Class 지시문
ms.date: 03/30/2017
f1_keywords:
- x:Class
- xClass
- Class
helpviewer_keywords:
- Class attribute in XAML [XAML Services]
- XAML [XAML Services], x:Class attribute
- x:Class attribute [XAML Services]
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
ms.openlocfilehash: 7e6a2379640d2556b553d14d20398a0a14931393
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="xclass-directive"></a>x:Class 지시문
XAML 태그 컴파일을 태그와 코드 숨김 클래스를 부분 가입을 구성 합니다. 별도 코드 파일에 코드 partial 클래스가 정의 되어는 [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)] 언어에서 반면 태그 partial 클래스는 일반적으로 XAML 컴파일하는 동안 코드를 생성 하 여 만듭니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```  
<object x:Class="namespace.classname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`namespace`|선택 사항입니다. 지정 된 [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] 로 식별 되는 partial 클래스를 포함 하는 네임 스페이스 `classname`합니다. 경우 `namespace` 점 (.) 지정 된 `namespace` 및 `classname`합니다. 설명 부분을 참조하세요.|  
|`classname`|필수. 지정 된 [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] 로드 된 XAML 및 해당 XAML에 대 한 코드 숨김을 연결 하는 partial 클래스의 이름입니다.|  
  
## <a name="dependencies"></a>종속성  
 `x:Class` XAML 프로덕션의 루트 요소에만 지정할 수 있습니다. `x:Class` XAML 프로덕션에 부모가 있는 모든 개체에서 올바르지 않습니다. 자세한 내용은 참조 [ \[MS-XAML\] 섹션 4.3.1.6](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.  
  
## <a name="remarks"></a>설명  
 `namespace` 값에는.NET Framework 프로그래밍에서 일반적인 기술 관련된 네임 스페이스, 이름 계층으로 구성 하는 추가 점이 포함 될 수 있습니다. 문자열의 마지막 점만 `x:Class` 구분 값 해석 됩니다 `namespace` 및 `classname.` 로 사용 되는 클래스 `x:Class` 중첩 클래스일 수 없습니다. 중첩 된 클래스에는 대 한 점의 의미를 확인 하기 때문에 허용 되지 않습니다 `x:Class` 중첩된 클래스는 허용 하는 경우 문자열 모호 합니다.  
  
 기존의 프로그래밍를 사용 하는 모델에서 `x:Class`, `x:Class` 사용할 수 없는 코드 숨김 있는 XAML 페이지 임을 의미에서 선택 사항입니다. 그러나 해당 기능도 XAML을 사용 하는 프레임 워크에서 구현 되는 빌드 작업 상호 작용 합니다. `x:Class` 기능 역할 XAML 지정 된 콘텐츠의 다양 한 분류 응용 프로그램 모델에 있고 해당 빌드 동작의 영향도 받습니다. XAML 이벤트 처리 특성 값 또는 인스턴스화하는 코드 숨김 클래스에서 정의 하는 클래스가 있는 사용자 지정 요소를 선언 하는 경우 제공 해야는 `x:Class` 지시문 참조 (또는 [X:subclass](../../../docs/framework/xaml-services/x-subclass-directive.md))에 코드 숨김에 대 한 적절 한 클래스입니다.  
  
 값은 `x:Class` 지시문 어셈블리 정보가 없는 하지만 클래스의 정규화 된 이름을 지정 하는 문자열 이어야 합니다 (해당 하는 <xref:System.Type.FullName%2A?displayProperty=nameWithType>). 간단한 응용 프로그램에 대 한 코드 숨김 (클래스 수준에서 코드 정의 시작 됨)을 이러한 방식으로 구성 된 경우 CLR 네임 스페이스 정보를 생략할 수 있습니다.  
  
 페이지 또는 응용 프로그램 정의 대 한 코드 숨김 파일 컴파일된 응용 프로그램을 생성 하 고 태그 컴파일을 포함 하는 프로젝트의 일부로 포함 되어 있는 코드 파일 내에 있어야 합니다. CLR 클래스에 대 한 이름 규칙을 따라야 합니다. 자세한 내용은 참조 [Framework 디자인 지침](../../../docs/standard/design-guidelines/index.md)합니다. 기본적으로 코드 숨김 클래스 여야 `public`이지만 사용 하 여 서로 다른 액세스 수준으로 정의할 수 있습니다는 [X:classmodifier 지시문](../../../docs/framework/xaml-services/x-classmodifier-directive.md)합니다.  
  
 이의 해석은 `x:Class` 특성에만 적용 됩니다 CLR 기반 XAML 구현에서 특히.NET Framework XAML 서비스에 있습니다. CLR에 기반 하지 않는 및.NET Framework XAML 서비스를 사용 하지 않는 다른 XAML 구현에는 XAML 태그를 연결 하 고 백업 하는 코드에 대 한 다른 해결 방법이 수식을 사용할 수 있습니다. 보다 일반적인 해석 하는 방법에 대 한 자세한 내용은 `x:Class`, 참조 [ \[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.  
  
 아키텍처의 의미의 특정 수준에서 `x:Class` .NET Framework XAML 서비스에 정의 되어 있지 않습니다. 즉,.NET Framework XAML 서비스는 xaml 태그 및 코드를 백업 합니다. 연결 된 프로그래밍 모델을 지정 하지 않습니다. 다른 용도 `x:Class` 지시문 XAML 태그 및 코드 숨김을 CLR 기반 연결 하는 방법을 정의 하기 위해 프로그래밍 모델 또는 응용 프로그램 모델을 사용 하는 특정 프레임 워크에 의해 구현 될 수 있습니다. 각 프레임에는 동작이 나 빌드 환경에 포함 해야 하는 특정 구성 요소 중 일부를 사용 하는 자체 빌드 작업이 포함 될 수 있습니다. 프레임 워크 내에서 코드 숨김에 사용 되는 특정 CLR 언어에 따라 빌드 작업도 달라질 수 있습니다.  
  
## <a name="xclass-in-the-wpf-programming-model"></a>X:class WPF 프로그래밍 모델  
 WPF 응용 프로그램 및 WPF 응용 프로그램 모델에서 `x:Class` 는 XAML 파일의 루트 및 컴파일되는 모든 요소에 대 한 특성으로 선언할 수 있습니다 (여기서 XAML ´ â는 WPF 응용 프로그램 프로젝트와 `Page` 빌드 작업), 또는 < c4 > <xref:System.Windows.Application>  컴파일된 WPF 응용 프로그램의 응용 프로그램 정의의 루트입니다. 선언 `x:Class` 외 페이지 루트 계정 또는 응용 프로그램 루트의 요소 또는 컴파일되지 않은 XAML 파일에서 컴파일 타임 오류가 발생 된 [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] 및 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] WPF XAML 컴파일러입니다. 다른 측면에 대 한 내용은 `x:Class` 참조 WPF의 처리, [WPF의 XAML 및 코드 숨김](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)합니다.  
  
## <a name="xclass-for-windows-workflow-foundation"></a>Windows Workflow Foundation에 대 한 x: 클래스  
 Windows Workflow Foundation에 대 한 `x:Class` XAML로만 작성 된 사용자 지정 활동의 클래스 이름, 또는 코드 숨김 활동 디자이너에 대 한 XAML 페이지의 partial 클래스의 이름을 지정 합니다.  
  
## <a name="silverlight-usage-notes"></a>Silverlight 사용 정보  
 `x:Class` Silverlight 용은 별도로 설명 되어 있습니다. 자세한 내용은 참조 [XAML Namespace (x:) 언어 기능 (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [x:Subclass 지시문](../../../docs/framework/xaml-services/x-subclass-directive.md)  
 [WPF에 대한 XAML 및 사용자 지정 클래스](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [x:ClassModifier 지시문](../../../docs/framework/xaml-services/x-classmodifier-directive.md)  
 [WPF에서 System.Xaml로 마이그레이션된 형식](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
