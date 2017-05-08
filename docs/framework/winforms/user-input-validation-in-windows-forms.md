---
title: "Windows Forms에서 사용자 입력 유효성 검사 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "사용자 입력, Windows Forms에서 유효성 검사"
  - "사용자 입력 유효성 검사, Windows Forms"
  - "유효성 검사, Windows Forms 사용자 입력"
  - "Windows Forms, 사용자 입력 유효성 검사"
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Windows Forms에서 사용자 입력 유효성 검사
사용자가 응용 프로그램에 데이터를 입력하는 경우 응용 프로그램에서 해당 데이터를 사용하기 전에 데이터가 유효한지 여부를 확인할 수 있습니다.  특정 텍스트 필드의 길이가 0이 아니도록 지정하거나, 필드의 형식이 전화 번호 또는 기타 올바른 데이터 형식이 되도록 지정하거나, 데이터베이스의 보안을 손상시킬 수 있는 안전하지 않은 문자가 문자열에 포함되지 않도록 지정할 수 있습니다.  Windows Forms에서는 여러 가지 방법을 통해 응용 프로그램에서 입력의 유효성을 검사할 수 있도록 합니다.  
  
## MaskedTextBox 컨트롤을 사용한 유효성 검사  
 데이터를 전화 번호나 부품 번호와 같이 정의된 형식으로 입력하게 하려는 경우 <xref:System.Windows.Forms.MaskedTextBox> 컨트롤을 사용하면 최소한의 코드로 빠르게 이 작업을 수행할 수 있습니다.  *마스크*는 텍스트 상자의 지정된 위치에 입력할 수 있는 문자를 지정하는 마스킹 언어의 문자로 구성된 문자열입니다.  컨트롤에 일련의 메시지가 표시됩니다.  숫자를 입력해야 할 곳에 문자를 입력하는 경우와 같이 사용자가 잘못된 내용을 입력하는 경우 컨트롤에서 입력 내용이 자동으로 거부됩니다.  
  
 <xref:System.Windows.Forms.MaskedTextBox>에서 사용하는 마스킹 언어는 융통성이 크기 때문에  필수 문자, 선택적 문자, 하이픈과 괄호 같은 리터럴 문자, 통화 문자 및 날짜 구분 기호를 지정하는 데 사용할 수 있습니다.  또한 컨트롤은 데이터 소스에 바인딩될 경우 잘 작동합니다.  즉, 데이터 바인딩의 <xref:System.Windows.Forms.Binding.Format> 이벤트를 사용하여 들어오는 데이터의 형식을 마스크에 맞도록 다시 지정할 수 있으며, <xref:System.Windows.Forms.Binding.Parse> 이벤트를 사용하여 나가는 데이터의 형식을 데이터 필드의 사양에 맞도록 다시 지정할 수 있습니다.  
  
 자세한 내용은 [MaskedTextBox 컨트롤](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)을 참조하십시오.  
  
## 이벤트 구동 유효성 검사  
 유효성 검사를 완전 프로그래밍 방식으로 제어하거나 복잡한 유효성 검사를 수행해야 하는 경우에는 대부분의 Windows Forms 컨트롤에 기본 제공되는 유효성 검사 이벤트를 사용해야 합니다.  자유 형식의 사용자 입력을 받는 각 컨트롤에는 컨트롤에 데이터 유효성 검사가 필요할 때마다 발생하는 <xref:System.Windows.Forms.Control.Validating> 이벤트가 있습니다.  <xref:System.Windows.Forms.Control.Validating> 이벤트 처리 메서드에서는 사용자 입력의 유효성 검사를 다양한 방식으로 수행할 수 있습니다.  예를 들어 우편 번호가 들어가야 하는 텍스트 상자가 있는 경우 다음과 같은 방식으로 유효성 검사를 수행할 수 있습니다.  
  
-   우편 번호가 특정 우편 번호 그룹에 속해야 하는 경우에는 입력에 대해 문자열 비교를 수행하여 사용자가 입력한 데이터의 유효성을 검사할 수 있습니다.  예를 들어 우편 번호가 {10001, 10002, 10003} 집합에 있어야 하는 경우에는 문자열 비교를 수행하여 데이터의 유효성을 검사할 수 있습니다.  
  
-   우편 번호가 특정 형태여야 하는 경우에는 정규식을 사용하여 사용자가 입력한 데이터의 유효성을 검사할 수 있습니다.  예를 들어 `#####` 또는 `#####-####` 폼의 유효성을 검사하려면 정규식 `^(\d{5})(-\d{4})?$`를 사용합니다.  `A#A #A#` 폼의 유효성을 검사하려면 정규식 `[A-Z]\d[A-Z] \d[A-Z]\d`를 사용합니다.  정규식에 대한 자세한 내용은 [.NET Framework 정규식](../../../docs/standard/base-types/regular-expressions.md) 및 [정규식 예제](../../../docs/standard/base-types/regular-expression-examples.md)를 참조하십시오.  
  
-   우편 번호가 유효한 미국 우편 번호여야 하는 경우에는 우편 번호 웹 서비스를 호출하여 사용자가 입력한 데이터의 유효성을 검사할 수 있습니다.  
  
 <xref:System.Windows.Forms.Control.Validating> 이벤트에는 <xref:System.ComponentModel.CancelEventArgs> 형식의 개체가 제공됩니다.  컨트롤의 데이터가 잘못되었음이 확인되면 이 개체의 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성을 `true`로 설정하여 <xref:System.Windows.Forms.Control.Validating> 이벤트를 취소할 수 있습니다.  <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성을 설정하지 않으면 Windows Forms은 해당 컨트롤에 대한 유효성 검사가 성공한 것으로 가정하고 <xref:System.Windows.Forms.Control.Validated> 이벤트를 발생시킵니다.  
  
 <xref:System.Windows.Controls.TextBox>의 전자 메일 주소에 대한 유효성을 검사하는 코드 예제를 보려면 <xref:System.Windows.Forms.Control.Validating>을 참조하십시오.  
  
### 데이터 바인딩 및 이벤트 구동 유효성 검사  
 유효성 검사는 데이터베이스 테이블과 같은 데이터 소스에 컨트롤을 바인딩한 경우 매우 유용합니다.  유효성 검사를 사용하면 컨트롤의 데이터가 데이터 소스에서 요구하는 형식과 일치하고, 안전하지 않을 수 있는 따옴표와 백슬래시 같은 특수 문자가 포함되지 않도록 할 수 있습니다.  
  
 데이터 바인딩을 사용할 경우 컨트롤의 데이터는 <xref:System.Windows.Forms.Control.Validating> 이벤트가 실행되는 동안 데이터 소스와 동기화됩니다.  <xref:System.Windows.Forms.Control.Validating> 이벤트를 취소하면 데이터는 데이터 소스와 동기화되지 않습니다.  
  
> [!IMPORTANT]
>  <xref:System.Windows.Forms.Control.Validating> 이벤트 이후에 발생하는 사용자 지정 유효성 검사가 있는 경우에는 데이터 바인딩에 영향을 주지 않습니다.  예를 들어 <xref:System.Windows.Forms.Control.Validated> 이벤트에 데이터 바인딩의 취소를 시도하는 코드가 있더라도 데이터 바인딩이 계속 발생합니다.  이 경우 <xref:System.Windows.Forms.Control.Validated> 이벤트에서 유효성 검사를 수행하려면 컨트롤의 **데이터 소스 업데이트 모드** 속성\(**\(Databindings\)**\\**\(Advanced\)** 아래\)을 **OnValidation**에서 **Never**로 변경하고 *Control*`.DataBindings["`*\<YOURFIELD\>*`"].WriteValue()`를 유효성 검사 코드에 추가합니다.  
  
### 암시적 유효성 검사와 명시적 유효성 검사  
 그렇다면 컨트롤의 데이터는 언제 유효성을 검사할까요?  이 시기는 개발자가 결정합니다.  응용 프로그램의 필요에 따라 암시적 유효성 검사 또는 명시적 유효성 검사를 사용할 수 있습니다.  
  
#### 암시적 유효성 검사  
 암시적 유효성 검사 방식에서는 사용자가 입력한 데이터의 유효성을 검사합니다.  컨트롤에 입력되는 데이터에 대한 유효성 검사는 눌려진 키를 읽는 방식으로 수행하거나, 좀 더 일반적으로는 사용자가 입력 포커스를 한 컨트롤에서 다음 컨트롤로 이동할 때마다 수행할 수 있습니다.  이 접근 방식은 사용자에게 데이터에 대한 피드백을 즉각적으로 제공하려는 경우에 유용합니다.  
  
 컨트롤에 대해 암시적 유효성 검사를 사용하려는 경우 해당 컨트롤의 <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> 속성을 `true`로 설정해야 합니다.  <xref:System.Windows.Forms.Control.Validating> 이벤트를 취소할 경우 <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>에 할당된 값에 따라 컨트롤의 동작이 결정됩니다.  <xref:System.Windows.Forms.AutoValidate>를 할당한 경우 이벤트를 취소하면 <xref:System.Windows.Forms.Control.Validated> 이벤트가 발생하지 않습니다.  입력 포커스는 사용자가 데이터를 유효한 입력으로 변경할 때까지 현재 컨트롤에 유지됩니다.  <xref:System.Windows.Forms.AutoValidate>를 할당한 경우 이벤트를 취소하면 <xref:System.Windows.Forms.Control.Validated> 이벤트가 발생하지 않지만 포커스는 다음 컨트롤로 이동합니다.  
  
 <xref:System.Windows.Forms.AutoValidate>을 <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> 속성에 할당하면 암시적 유효성 검사도 함께 사용할 수 없게 됩니다.  컨트롤의 유효성을 검사하려면 명시적 유효성 검사를 사용해야 합니다.  
  
#### 명시적 유효성 검사  
 명시적 유효성 검사 방식에서는 데이터의 유효성을 한 번에 검사합니다.  저장 단추 또는 다음 링크를 클릭하는 등의 사용자 작업에 대해 데이터의 유효성을 검사할 수 있습니다.  사용자 작업이 발생하면 다음 방법 중 하나로 명시적 유효성 검사를 트리거할 수 있습니다.  
  
-   <xref:System.Windows.Forms.ContainerControl.Validate%2A>를 호출하여 포커스를 잃은 마지막 컨트롤의 유효성을 검사합니다.  
  
-   <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A>을 호출하여 폼 또는 컨테이너 컨트롤에 있는 모든 자식 컨트롤의 유효성을 검사합니다.  
  
-   사용자 지정 메서드를 호출하여 컨트롤에 있는 데이터의 유효성을 수동으로 검사합니다.  
  
#### Windows Forms 컨트롤의 기본 암시적 유효성 검사 동작  
 <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> 속성은 Windows Forms 컨트롤마다 기본값이 다릅니다.  다음 표에서는 가장 일반적인 컨트롤과 해당 기본값을 보여 줍니다.  
  
|컨트롤|기본 유효성 검사 동작|  
|---------|------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate>|  
|<xref:System.Windows.Forms.PropertyGrid>|Visual Studio에서는 노출되지 않는 속성입니다.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Visual Studio에서는 노출되지 않는 속성입니다.|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate>|  
  
## 폼 닫기 및 유효성 검사 무시  
 포함된 데이터가 올바르지 않기 때문에 컨트롤에서 포커스가 이동하지 못하는 경우 다음과 같은 방법으로는 부모 폼을 닫을 수 없습니다.  
  
-   **닫기** 단추 클릭  
  
-   **시스템** 메뉴의 **닫기** 선택  
  
-   프로그래밍 방식으로 <xref:System.Windows.Forms.Form.Close%2A> 메서드 호출  
  
 그러나 컨트롤의 값이 올바른지 여부에 상관없이 사용자가 폼을 닫을 수 있도록 해야 하는 경우가 있습니다.  폼의 <xref:System.Windows.Forms.Form.Closing> 이벤트에 대한 처리기를 만들어 유효성 검사를 재정의하고 올바르지 않은 데이터가 들어 있는 폼을 닫을 수 있습니다.  이벤트에서 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성을 `false`로 설정합니다.  그러면 폼이 강제로 닫힙니다.  자세한 내용과 예제는 <xref:System.Windows.Forms.Form.Closing?displayProperty=fullName>을 참조하십시오.  
  
> [!NOTE]
>  이런 식으로 폼을 강제로 닫는 경우 폼의 컨트롤에 있는 저장되지 않은 데이터가 손실됩니다.  또한 모달 폼은 폼을 닫을 때 컨트롤 내용의 유효성을 검사하지 않습니다.  컨트롤 유효성 검사를 통해 컨트롤에 대한 포커스를 잠글 수는 있지만 폼을 닫는 동작에 대해서는 신경 쓸 필요가 없습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Control.Validating?displayProperty=fullName>   
 <xref:System.Windows.Forms.Form.Closing?displayProperty=fullName>   
 <xref:System.ComponentModel.CancelEventArgs?displayProperty=fullName>   
 [MaskedTextBox 컨트롤](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)   
 [정규식 예제](../../../docs/standard/base-types/regular-expression-examples.md)