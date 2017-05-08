---
title: "종속성 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# 종속성 속성
종속성 속성 \(DP\)은 예를 들어 형식 변수 \(필드\)를 저장 하는 대신 속성 저장소의 해당 값을 저장 하는 일반 속성입니다.  
  
 연결 된 종속성 속성은 개체와 해당 컨테이너 간의 관계를 설명 하는 "속성"을 나타내는 정적 Get 및 Set 메서드로 모델링 하는 종속성 속성의 종류 \(예: 위치는 `Button` 개체에 `Panel` 컨테이너\).  
  
 **✓ 수행** 스타일, 트리거, 데이터 바인딩, 애니메이션, 동적 리소스 및 상속과 같은 WPF 기능을 지원 하기 위해 속성을 필요한 경우 종속성 속성을 제공 합니다.  
  
## 종속성 속성 디자인  
 **✓ 수행** 에서 상속 <xref:System.Windows.DependencyObject>, 또는 종속성 속성을 구현 하는 경우 하위 유형 중 하나입니다. 형식을 속성 저장소의 효율적인 구현을 제공 하 고 자동으로 WPF 데이터 바인딩을 지원 합니다.  
  
 **✓ 수행** 일반 CLR 속성 및 인스턴스를 저장 합니다. 공용 정적 읽기 전용 필드를 제공 <xref:System.Windows.DependencyProperty?displayProperty=fullName> 각 종속성 속성에 있습니다.  
  
 **✓ 수행** 인스턴스 메서드를 호출 하 여 종속성 속성을 구현 <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=fullName> 및 <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=fullName>합니다.  
  
 **✓ 수행** "속성입니다."를 사용 하 여 속성의 이름을 붙여 하 여 종속성 속성의 정적 필드 이름을 지정  
  
 **X 하지 않으려면** 코드에서 종속성 속성의 기본값을 명시적으로 설정 하 고 대신 메타 데이터에서 설정 합니다.  
  
 속성 기본값을 명시적으로 설정 하면 해당 속성을 스타일 등 일부 암시적 방법으로 설정 되지 하지 못할 수도 있습니다.  
  
 **X 하지 않으려면** 정적 필드에 액세스 하는 표준 코드 이외의 속성 접근자에 코드를 입력 합니다.  
  
 정적 필드를 직접 사용 스타일을 지정 하기 때문에 속성이 설정 된 스타일을 같은 암시적 수단으로 하는 경우 코드가 실행 되지 않습니다.  
  
 **X 하지 않으려면** 종속성 속성을 사용 하 여 안전한 데이터를 저장 합니다. 비공개 종속성 속성은 공개적으로 액세스할 수 있습니다.  
  
## 연결 된 종속성 속성 디자인  
 이전 섹션에서 설명 하는 종속성 속성을 선언 형식의 기본 속성을 나타냅니다. 예를 들어는 `Text` 속성은 속성의 `TextButton`, 변수를 선언입니다. 종속성 속성의 특별 한 종류에는 연결 된 종속성 속성입니다.  
  
 연결된 된 속성의 전형적인 예로 <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=fullName> 속성입니다. 속성 단추 \(하지 표의\) 열의 위치를 나타내지만 관련 되는 것은 "연결" 단추를 표 여 고 단추는 눈금에 포함 된 경우.  
  
```  
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
  
    <Button Grid.Column="0">Click</Button>  
    <Button Grid.Column="1">Clack</Button>  
</Grid>  
```  
  
 연결된 된 속성의 정의 같습니다 대부분의 일반 종속성 속성을 제외 하 고 접근자는 정적 Get 및 Set 메서드를 통해 표현 됩니다.  
  
```  
public class Grid {  
  
    public static int GetColumn(DependencyObject obj) {  
        return (int)obj.GetValue(ColumnProperty);  
    }  
  
    public static void SetColumn(DependencyObject obj, int value) {  
        obj.SetValue(ColumnProperty,value);  
    }  
  
    public static readonly DependencyProperty ColumnProperty =  
        DependencyProperty.RegisterAttached(  
            "Column",  
            typeof(int),  
            typeof(Grid)  
    );  
}  
```  
  
## 종속성 속성의 유효성 검사  
 속성은 종종 유효성 검사에 영향을 주는 섞어 구현 합니다. 속성의 값을 변경 하려고 시도 하는 경우 유효성 검사 논리를 실행 합니다.  
  
 그러나 종속성 속성 접근자 임의의 유효성 검사 코드를 포함할 수 없습니다. 대신, 종속성 속성 유효성 검사 논리 속성을 등록할 때 지정 해야 합니다.  
  
 **X 하지 않으려면** 속성의 접근자에 종속성 속성 유효성 검사 논리를 배치 합니다. 대신에 대 한 유효성 검사 콜백 전달 `DependencyProperty.Register` 메서드.  
  
## 종속성 속성 변경 알림  
 **X 하지 않으려면** 종속성 속성 접근자에서 변경 알림을 논리를 구현 합니다. 종속성 속성에 대 한 변경 알림 콜백을 제공 하 여 사용 해야 하는 기본 제공 변경 알림 기능에는 <xref:System.Windows.PropertyMetadata>합니다.  
  
## 종속성 속성 값 강제 변환  
 속성 강제 변환 속성 저장소를 실제로 수정 하기 전에 속성 setter에 지정 된 값의 setter에서 수정할 때 수행이 됩니다.  
  
 **X 하지 않으려면** 종속성 속성 접근자에서 강제 변환 논리를 구현 합니다.  
  
 종속성 속성에 있는 기본 제공 강제 변환 기능을 하 고 강제 콜백을 제공 하 여 사용할 수는 `PropertyMetadata`합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [일반적인 디자인 패턴](../../../docs/standard/design-guidelines/common-design-patterns.md)