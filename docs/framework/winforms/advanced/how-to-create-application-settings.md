---
title: "방법: 응용 프로그램 설정 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], creating
ms.assetid: 1e7aa347-af75-41e5-89ca-f53cab704f72
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 481239b472ced5ef6251b665dad16e83a170607d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-application-settings"></a>방법: 응용 프로그램 설정 만들기
관리 코드를 사용하여 새 응용 프로그램 설정을 만들고, 이러한 설정이 런타임에 자동으로 로드 및 저장되도록 폼의 속성이나 폼의 컨트롤에 바인딩할 수 있습니다.  
  
 다음 절차에서는 <xref:System.Configuration.ApplicationSettingsBase>에서 파생되는 래퍼 클래스를 수동으로 만듭니다. 노출하려는 각 응용 프로그램 설정에 대한 공개적으로 액세스 가능한 속성을 이 클래스에 추가합니다.  
  
 Visual Studio 디자이너에서 최소한의 코드로 이 절차를 수행할 수도 있습니다.  참조도 [하는 방법: 응용 프로그램 설정을 사용 하 여 작성 디자이너](http://msdn.microsoft.com/library/wabtadw6\(v=vs.110\))합니다.  
  
### <a name="to-create-new-application-settings-programmatically"></a>새 응용 프로그램 설정을 프로그래밍 방식으로 만들려면  
  
1.  프로젝트에 새 클래스를 추가하고 이름을 바꿉니다. 이 절차에서는이 클래스 라고 합니다 `MyUserSettings`합니다. 클래스가 <xref:System.Configuration.ApplicationSettingsBase>에서 파생되도록 클래스 정의를 변경합니다.  
  
2.  필요한 각 응용 프로그램 설정에 대해 이 래퍼 클래스의 속성을 정의하고 설정의 범위에 따라 해당 속성을 <xref:System.Configuration.ApplicationScopedSettingAttribute> 또는 <xref:System.Configuration.UserScopedSettingAttribute>로 적용합니다. 설정 범위에 대 한 자세한 내용은 참조 [응용 프로그램 설정 개요](../../../../docs/framework/winforms/advanced/application-settings-overview.md)합니다. 지금까지 작성된 코드는 다음과 같습니다.  
  
     [!code-csharp[ApplicationSettings.Create#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
     [!code-vb[ApplicationSettings.Create#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
3.  응용 프로그램에서 이 래퍼 클래스의 인스턴스를 만듭니다. 일반적으로 기본 폼의 전용 멤버가 됩니다. 이제 클래스를 정의했으므로 속성(이 경우 폼의 <xref:System.Windows.Forms.Form.BackColor%2A> 속성)에 바인딩해야 합니다. 폼의에이 수행할 수 있습니다 `Load` 이벤트 처리기입니다.  
  
     [!code-csharp[ApplicationSettings.Create#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#2)]
     [!code-vb[ApplicationSettings.Create#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#2)]  
  
4.  런타임에 설정을 변경하는 방법을 제공하는 경우 폼을 닫을 때 사용자의 현재 설정을 디스크에 저장해야 합니다. 그러지 않으면 이러한 변경 내용이 손실됩니다.  
  
     [!code-csharp[ApplicationSettings.Create#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#3)]
     [!code-vb[ApplicationSettings.Create#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#3)]  
  
     이제 성공적으로 새 응용 프로그램 설정을 만들고 지정된 속성에 바인딩했습니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 기본 설정 공급자인 <xref:System.Configuration.LocalFileSettingsProvider>는 정보를 구성 파일에 일반 텍스트로 저장합니다. 이 경우 보안이 운영 체제에서 현재 사용자에 대해 제공하는 파일 액세스 보안으로 제한됩니다. 이 때문에 구성 파일에 정보를 저장할 때는 주의해야 합니다. 예를 들어 응용 프로그램 설정은 일반적으로 응용 프로그램의 데이터 저장소를 가리키는 연결 문자열을 저장하는 데 사용됩니다. 그러나 보안 문제 때문에 이러한 문자열은 암호를 포함하지 않아야 합니다. 연결 문자열에 대한 자세한 내용은 <xref:System.Configuration.SpecialSetting>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Configuration.SpecialSettingAttribute>  
 <xref:System.Configuration.LocalFileSettingsProvider>  
 [응용 프로그램 설정 개요](../../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [방법: 응용 프로그램 설정 유효성 검사](../../../../docs/framework/winforms/advanced/how-to-validate-application-settings.md)
