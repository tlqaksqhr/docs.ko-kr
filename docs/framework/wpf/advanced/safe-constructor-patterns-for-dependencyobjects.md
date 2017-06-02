---
title: "DependencyObject의 안전한 생성자 패턴 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "종속성 개체의 생성자 패턴"
  - "종속성 개체, 생성자 패턴"
  - "FXCop 도구"
ms.assetid: f704b81c-449a-47a4-ace1-9332e3cc6d60
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# DependencyObject의 안전한 생성자 패턴
생성자는 파생 클래스에 대한 생성자의 기본 초기화로 호출될 수 있으므로 일반적으로 클래스 생성자는 가상 메서드나 대리자와 같은 콜백을 호출하지 않아야 합니다.  가상 메서드 호출은 지정된 개체의 초기화가 끝나지 않은 상태에서 수행될 수 있습니다.  하지만 속성 시스템 자체에서는 종속성 속성 시스템의 일부로 내부에서 콜백을 호출하고 노출합니다.  이 작업은 <xref:System.Windows.DependencyObject.SetValue%2A> 호출을 사용하여 종속성 속성 값을 설정함으로써 간단하게 수행할 수 있지만 속성 값을 결정하는 과정에서 콜백이 포함될 수 있습니다.  이 때문에 생성자 본문 내에서 종속성 속성 값을 설정할 때는 신중을 기해야 합니다. 형식이 기본 클래스로 사용되는 경우에는 이로 인해 문제가 발생할 수도 있습니다.  이 항목에서는 종속성 속성 상태 및 고유 콜백과 관련된 문제가 발생하지 않도록 <xref:System.Windows.DependencyObject> 생성자를 구현하는 특수한 패턴에 대해 설명합니다.  
  
   
  
<a name="Property_System_Virtual_Methods"></a>   
## 속성 시스템 가상 메서드  
 종속성 속성 값을 설정하는 <xref:System.Windows.DependencyObject.SetValue%2A> 호출을 계산하는 동안 <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.PropertyChangedCallback>, <xref:System.Windows.CoerceValueCallback>, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> 가상 메서드 또는 콜백이 호출될 수 있습니다.  각 가상 메서드 또는 콜백은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 속성 시스템 및 종속성 속성의 다양성을 확장하는 데 사용됩니다.  이러한 가상 메서드를 사용하여 속성 값 결정을 사용자 지정하는 자세한 방법은 [종속성 속성 콜백 및 유효성 검사](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md)를 참조하십시오.  
  
### FXCop 규칙 적용과속성 시스템 가상 메서드  
 Microsoft에서 제공하는 FXCop 도구를 빌드 프로세스에 사용하고 기본 생성자를 호출하는 특정 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프레임워크 클래스에서 클래스를 파생하거나 파생된 클래스에 고유의 종속성 속성을 구현하는 경우 특정 FXCop 규칙 위반이 발생할 수도 있습니다.  이 위반의 이름 문자열은 다음과 같습니다.  
  
 `DoNotCallOverridableMethodsInConstructors`  
  
 이 규칙은 FXCop에 대한 기본 공용 규칙 집합의 일부입니다.  이 규칙이 보고하는 것은 종속성 속성 시스템을 통과하여 궁극적으로 종속성 속성 시스템 가상 메서드를 호출하는 추적입니다.  이 규칙 위반은 이 항목에서 설명하는 권장 생성자 패턴을 따른 후에도 계속해서 발생할 수 있으므로 FXCop 규칙 집합 구성에서 이 규칙을 비활성화하거나 해제하는 것이 좋습니다.  
  
### 기존 클래스 사용이 아니라 클래스 파생으로 인해 발생하는 대부분의 문제  
 이 규칙이 보고하는 문제는 클래스 생성 시퀀스에서 가상 메서드를 사용하여 구현한 클래스에서 다른 클래스를 파생할 때 발생합니다.  클래스를 봉인한 경우, 클래스가 파생되지 않는다는 것을 알고 있는 경우 또는 클래스가 파생되지 않도록 설정한 경우에는 이 항목에 설명된 FXCop 규칙 관련 문제를 염려할 필요가 없습니다.  하지만 기본 클래스로 사용할 클래스를 만드는 경우, 예를 들어 템플릿을 만들거나 확장 가능한 컨트롤 라이브러리 집합을 만드는 경우에는 여기에서 권장하는 생성자 패턴을 따라야 합니다.  
  
### 기본 생성자로 콜백이 요청하는 모든 값을 초기화해야 함  
 클래스 재정의 또는 콜백\(속성 시스템 가상 메서드 단원에 나오는 콜백\)이 사용하는 인스턴스 멤버는 클래스 기본 생성자에서 초기화되어야 합니다. 이는 값 중 일부가 기본 생성자가 아닌 생성자의 매개 변수를 통해 "실제" 값으로 채워지는 경우에도 마찬가지입니다.  
  
 다음 예제 코드 및 이후에 나오는 예제는 이 규칙을 위반하여 그로 인해 발생하는 문제에 대해 설명하는 의사\(pseudo\) C\# 예제입니다.  
  
```  
public class MyClass : DependencyObject  
{  
    public MyClass() {}  
    public MyClass(object toSetWobble)  
        : this()  
    {  
        Wobble = toSetWobble; //this is backed by a DependencyProperty  
        _myList = new ArrayList();    // this line should be in the default ctor  
    }  
    public static readonly DependencyProperty WobbleProperty =   
        DependencyProperty.Register("Wobble", typeof(object), typeof(MyClass));  
    public object Wobble  
    {  
        get { return GetValue(WobbleProperty); }  
        set { SetValue(WobbleProperty, value); }  
    }  
    protected override void OnPropertyChanged(DependencyPropertyChangedEventArgs e)  
    {  
        int count = _myList.Count;    // null-reference exception  
    }  
    private ArrayList _myList;  
}  
```  
  
 응용 프로그램 코드에서 호출할 경우 `new MyClass(objectvalue)`는 기본 생성자와 기본 클래스 생성자를 호출합니다.  그런 다음 `Property1 = object1`로 설정하여 소유하는 `MyClass` <xref:System.Windows.DependencyObject>에서 가상 메서드 `OnPropertyChanged`를 호출합니다.  이 재정의는 아직 초기화되지 않은 `_myList`를 참조합니다.  
  
 이러한 문제를 피하는 한 가지 방법은 콜백이 다른 종속성 속성만 사용하도록 하고 이러한 각 종속성 속성에 대해 등록하는 메타데이터의 일부로 속성의 기본값을 설정하는 것입니다.  
  
<a name="Safe_Constructor_Patterns"></a>   
## 안전한 생성자 패턴  
 클래스를 기본 클래스로 사용하는 경우 불완전한 초기화가 발생하지 않도록 하려면 다음 패턴을 따릅니다.  
  
#### 기본 생성자가 기본 초기화 호출  
 기본 생성자가 기본값을 호출하도록 구현합니다.  
  
```  
public MyClass : SomeBaseClass {  
    public MyClass() : base() {  
        // ALL class initialization, including initial defaults for   
        // possible values that other ctors specify or that callbacks need.  
    }  
}  
```  
  
#### 기본 생성자가 아닌\(편리한\) 생성자, 기본 시그니처와 일치하지 않음  
 이러한 생성자가 매개 변수를 사용하여 초기화에서 종속성 속성을 설정하는 경우 먼저 초기화할 고유 클래스의 기본 생성자를 호출한 다음 매개 변수를 사용하여 종속성 속성을 설정합니다.  이러한 종속성 속성은 클래스가 정의한 종속성 속성일 수도 있고 기본 클래스에서 상속된 종속성 속성일 수도 있습니다. 어떤 경우에 해당하든 다음 패턴을 사용합니다.  
  
```  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### 기본 생성자가 아닌\(편리한\) 생성자, 기본 시그니처와 일치함  
 동일한 매개 변수화를 사용하여 기본 생성자를 호출하는 대신 고유 클래스의 기본 생성자를 다시 호출합니다.  기본 이니셜라이저를 호출하는 대신 `this()`를 호출해야 합니다.  그런 다음 전달된 매개 변수를 값으로 사용하여 관련 속성을 설정함으로써 원래 생성자 동작을 재현합니다.  특정 매개 변수를 어떤 속성에 설정해야 하는지 확인하려면 원래 기본 생성자와 관련된 설명서를 참조하십시오.  
  
```  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### 모든 시그니처와 일치해야 함  
 기본 형식에 여러 개의 시그니처가 있는 경우, 추가 속성을 설정하기 전에 클래스 기본 생성자 호출에 대한 권장 패턴을 따르는 고유의 생성자를 구현하여 가능한 모든 시그니처와 일치시켜야 합니다.  
  
#### SetValue를 사용하여 종속성 속성 설정  
 편리한 속성 설정을 위한 래퍼가 없는 속성을 설정하며 <xref:System.Windows.DependencyObject.SetValue%2A>를 사용하여 값을 설정하는 경우 이와 동일한 패턴이 적용됩니다.  생성자 매개 변수를 통해 전달되는 <xref:System.Windows.DependencyObject.SetValue%2A> 호출은 초기화할 클래스의 기본 생성자도 호출해야 합니다.  
  
## 참고 항목  
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [종속성 속성 보안](../../../../docs/framework/wpf/advanced/dependency-property-security.md)