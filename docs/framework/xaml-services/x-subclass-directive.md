---
title: x:Subclass 지시문
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: b04982ff0b7685b4e4b809255e3bbe541b42cb9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566420"
---
# <a name="xsubclass-directive"></a>x:Subclass 지시문
XAML 태그 컴파일 동작을 수정 하는 경우 `x:Class` 도 제공 됩니다. 기반으로 하는 partial 클래스를 만드는 대신 `x:Class`, 제공 된 `x:Class` 중간 클래스로 생성 한 다음 제공 된 파생된 클래스는 기반으로 해야 하 고 `x:Class`합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`namespace`|선택 사항입니다. 포함 된 CLR 네임 스페이스 지정 `classname`합니다. 경우 `namespace` 점 (.) 지정 된 `namespace` 및 `classname`합니다.|  
|`classname`|필수. 로드 된 XAML 및 해당 XAML에 대 한 코드 숨김을 연결 하는 partial 클래스의 CLR 이름을 지정 합니다. 설명 부분을 참조하세요.|  
|`subclassNamespace`|선택 사항입니다. 다를 수 있습니다 `namespace` 각 네임 스페이스는 다른 확인할 수 있는 경우. 포함 된 CLR 네임 스페이스 지정 `subclassName`합니다. 경우 `subclassName` 점 (.) 지정 된 `subclassNamespace` 및 `subclassName`합니다.|  
|`subclassName`|필수. 하위 클래스의 CLR 이름을 지정합니다.|  
  
## <a name="dependencies"></a>종속성  
 [X:class 지시문](../../../docs/framework/xaml-services/x-class-directive.md) 동일한 개체에도 제공 해야 하며 해당 개체에는 XAML 프로덕션의 루트 요소 이어야 합니다.  
  
## <a name="remarks"></a>설명  
 `x:Subclass` 부분 클래스 선언만 지원 하지 않는 언어에 대 한 사용 현황 주로 됩니다.  
  
 로 사용 되는 클래스는 `x:Subclass` 중첩된 클래스일 수 없습니다 및 `x:Subclass` "종속성" 섹션에 설명 된 대로 루트 개체를 참조 해야 합니다.  
  
 그렇지 않은 경우의 개념적 의미 `x:Subclass` .NET Framework XAML 서비스 구현으로 정의 되어 있지 않습니다. 즉,.NET Framework XAML 서비스 동작이 있는 xaml 태그 및 코드를 백업 합니다. 연결 된 전체 프로그래밍 모델을 지정 하지 않습니다. 와 관련 된 추가 개념 구현 `x:Class` 및 `x:Subclass` 프로그래밍 모델 또는 응용 프로그램 모델을 사용 하 여 XAML 태그, 컴파일된 태그 및 코드 숨김을 CLR 기반 연결 하는 방법을 정의 하는 특정 프레임 워크에 의해 수행 됩니다. 각 프레임에는 동작 또는 빌드 환경에 포함 해야 하는 특정 구성 요소 중 일부를 사용 하는 자체 빌드 작업이 포함 될 수 있습니다. 프레임 워크 내에서 빌드 작업 이면의 코드에 사용 되는 특정 CLR 언어에 따라 다 수도 있습니다.  
  
## <a name="wpf-usage-notes"></a>WPF 사용 정보  
 `x:Subclass` 페이지 루트 또는 가능는 <xref:System.Windows.Application> 이미 있는 응용 프로그램 정의에 루트 `x:Class`합니다. 선언 `x:Subclass` 페이지나 응용 프로그램 루트 또는 없는 위치에서 지정 이외의 모든 요소에 대해 `x:Class` 존재, 컴파일 타임 오류가 발생 합니다.  
  
 파생 클래스를 만드는 올바르게 동작 하는 `x:Subclass` 시나리오는 매우 복잡 합니다. 중간 파일 (.g 태그 컴파일 이름이.xaml 파일 이름을 통합 하 여 프로젝트의 obj 폴더에 생성 된 파일)을 검사 해야 합니다. 이러한 중간 파일의 컴파일된 응용 프로그램에 결합된 된 partial 클래스 프로그래밍 구문의 출처를 확인할 수 있습니다.  
  
 파생된 클래스에서 이벤트 처리기 해야 `internal override` (`Friend Overrides` Microsoft Visual Basic) 컴파일하는 동안 중간 클래스에서 생성 되는 처리기에 대 한 스텁의 재정의 하기 위해. 그렇지 않으면 파생된 클래스 구현은 숨기고 중간 클래스 구현 및 중간 클래스 처리기가 호출 되지 않습니다.  
  
 둘 다 정의 하는 경우 `x:Class` 및 `x:Subclass`에서 참조 되는 클래스에 대 한 구현을 제공할 필요가 없습니다 `x:Class`합니다. 통해 이름을 지정 하기만 하면는 `x:Class` 특성 컴파일러 중간 파일 (컴파일러 선택 하지 못하는 기본 이름이 경우)에 생성 된 클래스에 대 한 몇 가지 지침을 갖도록 합니다. 제공할 수 있습니다는 `x:Class` 구현 클래스 이며 이때는 둘 다를 사용 하는 일반적인 시나리오 `x:Class` 및 `x:Subclass`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [x:Class 지시문](../../../docs/framework/xaml-services/x-class-directive.md)  
 [WPF에 대한 XAML 및 사용자 지정 클래스](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
