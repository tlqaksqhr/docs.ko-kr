---
title: "Windows Forms에서 사용자 입력 유효성 검사"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1eba92d764e73360b1cd58957ea5318c5b263b8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="user-input-validation-in-windows-forms"></a>Windows Forms에서 사용자 입력 유효성 검사
사용자가 응용 프로그램에 데이터를 입력 하면 응용 프로그램에 사용 하기 전에 데이터가 유효한 지 확인 하는 것이 좋습니다. 특정 텍스트 필드 길이가 0 인 전화 번호 또는 다른 종류의 올바른 형식의 데이터 필드를 지정 하거나, 하거나 문자열에 데이터베이스의 보안을 손상 하기 위해 사용할 수 있는 안전 하지 않은 문자가 포함 되지 않도록 필요할 수 있습니다. Windows Forms 응용 프로그램에서 입력의 유효성을 검사 하는 여러 가지 방법을 제공 합니다.  
  
## <a name="validation-with-the-maskedtextbox-control"></a>MaskedTextBox 컨트롤 유효성 검사  
 사용자가 전화 번호 또는 부품 번호 등의 잘 정의 된 형식으로 데이터를 입력 하도록 하는 경우이 수행할 수 있습니다 신속 하 고 최소한의 코드를 사용 하 여는 <xref:System.Windows.Forms.MaskedTextBox> 제어 합니다. A *마스크* 문자로 텍스트 상자에 지정된 된 위치에 있는 문자를 입력할 수를 지정 하는 마스킹 언어에서 구성 된 문자열입니다. 컨트롤에 사용자에 게 표시 되는 메시지 집합이 표시 됩니다. 예를 들어 사용자가 잘못 된 항목을 숫자가 필요한 경우 사용자는 문자를 입력, 컨트롤의 입력을 자동으로 거부 됩니다.  
  
 사용 되는 마스킹 언어 <xref:System.Windows.Forms.MaskedTextBox> 매우 유연 합니다. 필요한 문자, 필요에 따라 문자, 하이픈 및 괄호 같은 리터럴 문자, 통화 문자 및 날짜 구분 기호를 지정할 수 있습니다. 컨트롤을 데이터 원본에 바인딩될 경우 잘 에서도 작동 합니다. <xref:System.Windows.Forms.Binding.Format> 마스크를 충족 하기 위해 들어오는 데이터의 서식을 다시 지정에서 데이터 바인딩 이벤트를 사용할 수 및 <xref:System.Windows.Forms.Binding.Parse> 데이터 필드의 사양을 준수 하도록 보내는 데이터의 서식을 다시 지정 이벤트를 사용할 수 있습니다.  
  
 자세한 내용은 참조 [MaskedTextBox 컨트롤](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)합니다.  
  
## <a name="event-driven-validation"></a>이벤트 기반 유효성 검사  
 유효성 검사를 보다 완전 프로그래밍 방식으로 제어 하려면 하거나 복잡 한 유효성 검사를 수행 해야 할 경우에 대부분의 Windows Forms 컨트롤에 기본 제공 유효성 검사 이벤트를 사용 해야 합니다. 자유 형식 사용자 입력을 허용 하는 각 컨트롤에는 <xref:System.Windows.Forms.Control.Validating> 컨트롤에 필요한 데이터 유효성 검사 될 때마다 발생 하는 이벤트입니다. 에 <xref:System.Windows.Forms.Control.Validating> 이벤트 처리 메서드를 여러 가지 방법으로의 사용자 입력 검증할 수 있습니다. 예를 들어 우편 번호를 포함 해야 하는 텍스트 상자가 설정한 경우 다음과 같은 방법으로 유효성 검사를 수행할 수 있습니다.  
  
-   우편 번호 zip 코드의 특정 그룹에 속해야 합니다, 경우에 사용자가 입력 한 데이터 유효성 검사에 대 한 입력 문자열 비교를 수행할 수 있습니다. 예를 들어 우편 번호는 {10001, 10002, 10003} 집합에 수 있어야 할 경우 문자열 비교를 사용 하 여 데이터 유효성 검사 수 있습니다.  
  
-   우편 번호 특정 폼에 있어야 하는 경우 사용자가 입력 한 데이터 유효성 검사 정규식을 사용할 수 있습니다. 예를 들어 양식에 유효성을 검사 하려면 `#####` 또는 `#####-####`, 정규식을 사용할 수 있습니다 `^(\d{5})(-\d{4})?$`합니다. 폼 유효성을 검사 하려면 `A#A #A#`, 정규식을 사용할 수 있습니다 `[A-Z]\d[A-Z] \d[A-Z]\d`합니다. 정규식에 대 한 자세한 내용은 참조 [.NET Framework 정규식](../../../docs/standard/base-types/regular-expressions.md) 및 [일반 식 예제](../../../docs/standard/base-types/regular-expression-examples.md)합니다.  
  
-   우편 번호에 유효한 미국 우편 번호 여야 합니다, 우편 번호 웹 서비스는 사용자가 입력 한 데이터 유효성 검사를 호출할 수 있습니다.  
  
 <xref:System.Windows.Forms.Control.Validating> 이벤트를 제공 하는 형식의 개체로 <xref:System.ComponentModel.CancelEventArgs>합니다. 컨트롤의 데이터가 유효한 지를 확인 하는 경우를 취소할 수는 <xref:System.Windows.Forms.Control.Validating> 이 개체를 설정 하 여 이벤트 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성을 `true`합니다. 설정 하지 않은 경우는 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성, Windows Forms 해당 유효성 검사는 해당 컨트롤에 대 한 성공 가정 되며 발생는 <xref:System.Windows.Forms.Control.Validated> 이벤트입니다.  
  
 전자 메일 주소 유효성을 검사 하는 코드 예제는 <xref:System.Windows.Controls.TextBox>, 참조 <xref:System.Windows.Forms.Control.Validating>합니다.  
  
### <a name="data-binding-and-event-driven-validation"></a>데이터 바인딩 및 이벤트 기반 유효성 검사  
 유효성 검사 컨트롤 데이터베이스 테이블과 같은 데이터 소스에 바인딩한 경우 매우 유용 합니다. 하도록 하는 유효성 검사를 사용 하 여 컨트롤의 데이터가 데이터 원본에 필요한 형식과 일치 하는 것 않습니다 하지 인용 부호와 같은 특수 문자를 포함할와 백슬래시는 안전 하지 않을 수 있습니다.  
  
 컨트롤에서 데이터가 데이터 바인딩을 사용 하면 실행 하는 동안 데이터 소스와 동기화 되었는지는 <xref:System.Windows.Forms.Control.Validating> 이벤트입니다. 취소 하는 경우는 <xref:System.Windows.Forms.Control.Validating> 이벤트 데이터를 데이터 소스와 동기화 되지 것입니다.  
  
> [!IMPORTANT]
>  사용자 지정 유효성 검사 후 발생 하는 경우는 <xref:System.Windows.Forms.Control.Validating> 이벤트는 달라 지지 것입니다 데이터 바인딩. 예를 들어, 코드를 있는 경우는 <xref:System.Windows.Forms.Control.Validated> 데이터 바인딩을 취소 하려고 시도 하는 이벤트, 데이터 바인딩 계속 발생 합니다. 이 경우에서 유효성 검사를 수행 하는 <xref:System.Windows.Forms.Control.Validated> 이벤트를 컨트롤의 변경 **데이터 원본 업데이트 모드** 속성 (**(Databindings)에서**\\**(고급)** )에서 **OnValidation** 를 **Never**, 추가 *제어*`.DataBindings["`*\<YOURFIELD >*  `"].WriteValue()` 유효성 검사 코드에 있습니다.  
  
### <a name="implicit-and-explicit-validation"></a>암시적 및 명시적 유효성 검사  
 따라서 때는 컨트롤의 데이터 한 유효성 검사를? 사용자, 개발자의 책임입니다. 응용 프로그램의 필요에 따라 암시적 또는 명시적 유효성 검사를 사용할 수 있습니다.  
  
#### <a name="implicit-validation"></a>암시적 유효성 검사  
 암시적 유효성 검사 방식 사용자가 해당 데이터의 유효성을 검사 합니다. 사용자가 입력된 포커스 제어를 사용 하 고 다음으로 이동 될 때마다 일반적으로 데이터 키를 누를 읽는로 컨트롤 이상으로 입력 데이터를 확인할 수 있습니다. 이 방법은 작업 데이터에 대 한 사용자 즉각적인 피드백을 제공 하려는 경우에 유용 합니다.  
  
 컨트롤에 대 한 암시적 유효성 검사를 사용 하려는 경우에 해당 컨트롤의 설정 해야 <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> 속성을 `true`합니다. 취소 하는 경우는 <xref:System.Windows.Forms.Control.Validating> 이벤트에는 컨트롤의 동작에 할당 하는 값에 의해 결정 됩니다 <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>합니다. 할당 한 경우 <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>, 이벤트를 취소는 <xref:System.Windows.Forms.Control.Validated> 이벤트를 발생 합니다. 사용자 입력에는 데이터를 변경할 때까지 현재 컨트롤에 입력된 포커스 유지 됩니다. 할당 한 경우 <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>, <xref:System.Windows.Forms.Control.Validated> 이벤트를 취소 하지만 포커스 다음 컨트롤로 때 이벤트가 발생 하지 것입니다.  
  
 할당 <xref:System.Windows.Forms.AutoValidate.Disable> 에 <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> 암시적 유효성 검사를 모두 방지 속성입니다. 컨트롤의 유효성을 검사 하려면 명시적 유효성 검사를 사용 해야 합니다.  
  
#### <a name="explicit-validation"></a>명시적 유효성 검사  
 명시적 유효성 검사 방법은 데이터를 한 번에 확인합니다. 저장 단추 또는 다음 링크를 클릭 하는 등의 사용자 작업에 대 한 응답에서 데이터를 확인할 수 있습니다. 사용자 작업이 발생 하는 경우 다음 방법 중 하나로 명시적 유효성 검사를 트리거할 수 있습니다.  
  
-   호출 <xref:System.Windows.Forms.ContainerControl.Validate%2A> 에 포커스를 잃은 마지막 컨트롤의 유효성을 검사 합니다.  
  
-   호출 <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> 를 폼 이나 컨테이너 컨트롤로의 모든 자식 컨트롤의 유효성을 검사 합니다.  
  
-   컨트롤의 데이터를 수동으로 유효성을 검사 하는 사용자 지정 메서드를 호출 합니다.  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>기본 암시적 유효성 검사 동작에 대 한 Windows Forms 컨트롤  
 다른 Windows Forms 컨트롤에 대 한 기본값은 다를 자신의 <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> 속성입니다. 다음 표에서 가장 일반적인 컨트롤과 해당 기본값을 보여 줍니다.  
  
|Control|기본 유효성 검사 동작|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|Visual Studio에서 노출 되지 않지만 속성|  
|<xref:System.Windows.Forms.ToolStripContainer>|Visual Studio에서 노출 되지 않지만 속성|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>양식을 닫기 및 유효성 검사 무시  
 컨트롤에서 포함 된 데이터가 유효 하지 않아서 포커스가 때 일반적인 방법 중 하나로 부모 폼을 닫을 수 없으면:  
  
-   클릭 하 여는 **닫기** 단추입니다.  
  
-   선택 하 여 **닫기** 에 **시스템** 메뉴.  
  
-   호출 하 여는 <xref:System.Windows.Forms.Form.Close%2A> 메서드 프로그래밍 방식으로 합니다.  
  
 하지만, 경우에 따라 컨트롤의 값이 올바른지 여부에 관계 없이 폼을 닫을 수 있도록 필요할 수 있습니다. 유효성 검사를 무시 하 고 폼의에 대 한 처리기를 만들고 잘못 된 데이터를 여전히 포함 되어 있는 폼을 닫을 수도 <xref:System.Windows.Forms.Form.Closing> 이벤트입니다. 이벤트에 설정 된 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성을 `false`합니다. 이렇게 하면 폼을 닫습니다. 자세한 내용과 예제는 <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>를 참조하세요.  
  
> [!NOTE]
>  해당 폼을 이런이 방식으로 실행 하면 저장 되지 않은 폼의 컨트롤에서 모든 데이터는 손실 됩니다. 또한 모달 폼 닫을 때 컨트롤의 내용을 확인 하지 않습니다. 컨트롤에 포커스를 잠그려면 컨트롤 유효성 검사를 계속 사용할 수 있습니다 하지만 양식을 닫기와 관련 된 동작에 대 한 신경 쓸 필요가 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
 <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType>  
 [MaskedTextBox 컨트롤](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)  
 [정규식 예제](../../../docs/standard/base-types/regular-expression-examples.md)
