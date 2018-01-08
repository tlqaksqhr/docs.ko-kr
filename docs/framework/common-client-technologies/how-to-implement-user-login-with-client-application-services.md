---
title: "방법: 클라이언트 응용 프로그램 서비스에서 사용자 로그인 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating users [client application services]
- validation [.NET Framework], client application services
- client application services, authenticate users
ms.assetid: 5431a671-eb02-4e18-a651-24764fccec9a
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2bf073b6db0a69cfda0c69ae34df0396f5dea35c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-user-login-with-client-application-services"></a>방법: 클라이언트 응용 프로그램 서비스에서 사용자 로그인 구현
클라이언트 응용 프로그램 서비스를 사용하면 기존의 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 프로필 서비스를 통해 사용자의 유효성을 검사할 수 있습니다. [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 프로필 서비스를 설정하는 방법에 대한 자세한 내용은 [ASP.NET AJAX와 함께 양식 인증 사용](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)을 참조하세요.  
  
 다음 절차에서는 응용 프로그램이 클라이언트 인증 서비스 공급자 중 하나를 사용하도록 구성된 경우 인증 서비스를 통해 사용자의 유효성을 검사하는 방법을 설명합니다. 자세한 내용은 [방법: 클라이언트 응용 프로그램 서비스 구성](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)을 참조하세요.  
  
 일반적으로 `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> 메서드를 통해 모든 유효성 검사를 수행합니다. 이 메서드는 구성된 인증 공급자를 통해 인증 서비스와의 상호 작용을 관리합니다. 자세한 내용은 [클라이언트 응용 프로그램 서비스 개요](../../../docs/framework/common-client-technologies/client-application-services-overview.md)를 참조하세요.  
  
 양식 인증 프로시저를 수행하려면 실행 중인 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 인증 서비스에 액세스해야 합니다. 클라이언트 응용 프로그램 서비스 기능의 종단 간 테스트 지침은 [연습: 클라이언트 응용 프로그램 서비스 사용](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)을 참조하세요.  
  
### <a name="to-authenticate-a-user-with-forms-authentication-using-a-membership-credentials-provider"></a>멤버 자격 증명 공급자를 사용하여 폼 인증으로 사용자를 인증하려면  
  
1.  <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> 인터페이스를 구현합니다. 다음 코드 예제에서는 <xref:System.Windows.Forms.Form?displayProperty=nameWithType>에서 파생된 로그인 대화 상자 클래스에 대한 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A?displayProperty=nameWithType> 구현을 보여 줍니다. 이 대화 상자에는 사용자 이름 및 암호 텍스트 상자와 "암호 저장" 확인란이 있습니다. 클라이언트 인증 공급자가 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 메서드를 호출하는 경우 폼이 표시됩니다. 사용자가 로그인 대화 상자에 정보를 채우고 확인을 클릭하면 지정한 값이 새 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials> 개체에 반환됩니다.  
  
     [!code-csharp[ClientApplicationServices#210](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Login.cs#210)]
     [!code-vb[ClientApplicationServices#210](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#210)]  
  
2.  `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> 메서드를 호출하고 빈 문자열을 매개 변수 값으로 전달합니다. 빈 문자열을 지정하는 경우 이 메서드는 응용 프로그램에 대해 구성된 자격 증명 공급자의 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 메서드를 내부적으로 호출합니다. 다음 코드 예제에서는 이 메서드를 호출하여 전체 Windows Forms 응용 프로그램에 대한 액세스를 제한합니다. <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> 처리기에 이 코드를 추가할 수 있습니다.  
  
     [!code-csharp[ClientApplicationServices#317](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#317)]
     [!code-vb[ClientApplicationServices#317](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#317)]  
  
### <a name="to-authenticate-a-user-with-forms-authentication-without-using-a-membership-credentials-provider"></a>멤버 자격 증명 공급자를 사용하지 않고 폼 인증으로 사용자를 인증하려면  
  
-   `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> 메서드를 호출하고 사용자로부터 받은 사용자 이름 및 암호 값을 전달합니다.  
  
     [!code-csharp[ClientApplicationServices#318](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#318)]
     [!code-vb[ClientApplicationServices#318](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#318)]  
  
### <a name="to-authenticate-a-user-with-windows-authentication"></a>Windows 인증으로 사용자를 인증하려면  
  
-   `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> 메서드를 호출하고 매개 변수에 대해 빈 문자열을 전달합니다. 이 메서드 호출은 항상 `true`를 반환하며 Windows ID를 포함하는 사용자의 쿠키 캐시에 쿠키를 추가합니다.  
  
     [!code-csharp[ClientApplicationServices#319](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#319)]
     [!code-vb[ClientApplicationServices#319](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#319)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 이 항목의 예제 코드에서는 Windows 클라이언트 응용 프로그램의 가장 간단한 인증 사용법을 보여 줍니다. 그러나 클라이언트 응용 프로그램 서비스 및 폼 인증을 사용하여 `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> 메서드를 호출하는 경우 코드에서 <xref:System.Net.WebException>이 발생할 수 있습니다. 이 예외는 인증 서비스를 사용할 수 없음을 나타냅니다. 이 예외를 처리하는 방법의 예는 [연습: 클라이언트 응용 프로그램 서비스 사용](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [클라이언트 응용 프로그램 서비스](../../../docs/framework/common-client-technologies/client-application-services.md)  
 [클라이언트 응용 프로그램 서비스 개요](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 [방법: 클라이언트 응용 프로그램 서비스 구성](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 [연습: 클라이언트 응용 프로그램 서비스 사용](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 [Microsoft Ajax에서 양식 인증 사용](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)
