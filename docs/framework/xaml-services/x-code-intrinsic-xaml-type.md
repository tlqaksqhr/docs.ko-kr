---
title: x:Code 내장 XAML 형식
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 92be0b3b0fd1212c4254a449f902b85e998aa148
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="xcode-intrinsic-xaml-type"></a>x:Code 내장 XAML 형식
XAML 프로덕션 내에서 코드를 배치할 수 있습니다. 이러한 코드는 런타임에 의해 해석 같이 나중에 사용에 대 한 XAML 프로덕션의 왼쪽 또는 XAML을 컴파일하는 XAML 프로세서 구현 하거나 컴파일될 수 있습니다.  
  
## <a name="xaml-object-element-usage"></a>XAML 개체 요소 사용  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a>설명  
 내의 코드는 `x:Code` XAML 지시문 요소는 일반 XML 네임 스페이스 내에서 해석 된 상태 및 제공 하는 XAML 네임 스페이스입니다. 따라서 것이 일반적으로에 사용 되는 코드를 포함 하는 데 필요한 `x:Code` 내는 `CDATA` 세그먼트입니다.  
  
 `x:Code` XAML 프로덕션의 모든 가능한 배포 메커니즘에 대해 허용 되지 않습니다. 특정 프레임 워크 (예: WPF) 코드를 컴파일해야 합니다. 다른 프레임 워크에서 `x:Code` 사용은 일반적으로 허용 될 수 있습니다.  
  
 관리 되는 허용 하는 프레임 워크에 대해 `x:Code` 콘텐츠에 사용할 언어 컴파일러 `x:Code` 내용은 포함 하는 응용 프로그램을 컴파일하는 데 사용 되는 프로젝트의 설정 및 대상에 의해 결정 됩니다.  
  
## <a name="wpf-usage-notes"></a>WPF 사용 정보  
 코드 내에서 선언 `x:Code` for WPF에 주목할 만한 몇 가지 제한이 있습니다.  
  
-   `x:Code` 지시문 요소 XAML 프로덕션의 루트 요소의 직접 자식 요소 여야 합니다.  
  
-   [X:class 지시문](../../../docs/framework/xaml-services/x-class-directive.md) 부모 root 요소에 제공 해야 합니다.  
  
-   내 코드에 배치 `x:Code` 컴파일 해당 XAML 페이지에 대해 이미 생성 된 하는 partial 클래스의 범위 내에 있는 것으로 취급 됩니다. 따라서 정의한 모든 코드는 해당 partial 클래스의 멤버 또는 변수 여야 합니다.  
  
-   Partial 클래스 안에 중첩 하 여 아닌 다른 추가 클래스를 정의할 수 없습니다 (중첩이 허용 하지만 중첩 된 클래스는 XAML에서 참조할 수 없으므로 일반적인 하지 않음). 기존 partial 클래스에 사용 되는 네임 스페이스 이외의 CLR 네임 스페이스를 정의 하거나에 추가 될 수 없습니다.  
  
-   Partial 클래스 CLR 네임 스페이스 외부 코드 엔터티에 대 한 참조는 모두 정규화 해야 합니다. 멤버 선언 되는 partial 클래스 재정의 가능한 멤버를 재정의 인이 언어별 재정의 키워드와 함께 지정 해야 합니다. 멤버에 선언 된 경우 `x:Code` 범위 XAML에서 생성 하는 partial 클래스의 멤버와 충돌, 방식에서 컴파일러가 충돌을 보고 XAML 파일 없습니다 컴파일 또는 로드 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [x:Class 지시문](../../../docs/framework/xaml-services/x-class-directive.md)  
 [WPF의 코드 숨김 및 XAML](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [XAML 개요(WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
