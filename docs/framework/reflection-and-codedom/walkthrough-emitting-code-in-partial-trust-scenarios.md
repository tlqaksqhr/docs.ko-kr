---
title: "연습: 부분 신뢰 시나리오에서 코드 내보내기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "익명으로 호스팅된 동적 메서드[.NET Framework]"
  - "동적 메서드"
  - "동적 어셈블리 내보내기, 부분 신뢰 시나리오"
  - "부분 신뢰, 동적 메서드 내보내기"
  - "부분 신뢰, 리플렉션"
  - "리플렉션 내보내기, 익명으로 호스팅된 동적 메서드"
  - "리플렉션 내보내기, 동적 메서드"
  - "리플렉션 내보내기, 부분 신뢰 시나리오"
ms.assetid: c45be261-2a9d-4c4e-9bd6-27f0931b7d25
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 연습: 부분 신뢰 시나리오에서 코드 내보내기
리플렉션 내보내기는 완전 또는 부분 신뢰에서 동일한 API 집합을 사용하지만 부분 신뢰 코드에서는 특별한 권한이 있어야 일부 기능을 사용할 수 있습니다.  또한 리플렉션 내보내기는 보안 투명 어셈블리에서 부분 신뢰 수준으로 사용되도록 설계된 익명으로 호스팅된 동적 메서드라는 기능이 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)] 이전에는 코드를 내보내려면 <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName> 플래그가 설정된 <xref:System.Security.Permissions.ReflectionPermission>이 필요했습니다.  이 권한은 `FullTrust` 및 `Intranet` 명명된 권한 집합에는 기본적으로 포함되어 있지만 `Internet` 권한 집합에는 포함되어 있지 않습니다.  따라서, 이 것이 <xref:System.Security.SecurityCriticalAttribute> 특성을 갖고 <xref:System.Security.Permissions.ReflectionPermissionFlag>에 대한 <xref:System.Security.PermissionSet.Assert%2A> 메서드를 실행하는 것에 대한 부분 신뢰를 가질때 라이브러리를 사용할 수 있습니다.  코드 오류가 있으면 보안에 문제가 생길 수 있으므로 이러한 라이브러리를 보안 측면에서 자세히 검토해야 합니다.  [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)]의 경우에는 기본적으로 코드를 생성하는 데 권한이 필요하지 않으므로 부분 신뢰 시나리오에서 보안 요구 사항 없이 코드를 내보낼 수 있습니다.  즉, 생성된 코드에는 이를 내보내는 어셈블리보다 많은 권한이 부여되지 않습니다.  따라서 코드를 내보내는 라이브러리에 대한 보안이 문제가 되지 않고 <xref:System.Security.Permissions.ReflectionPermissionFlag>을 어설션할 필요가 없으므로 보안에 크게 신경쓰지 않고도 안전한 라이브러리를 작성할 수 있습니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   [부분 신뢰 코드를 테스트하기 위한 간단한 샌드박스 설정](#Setting_up).  
  
    > [!IMPORTANT]
    >  샌드박스를 사용하면 부분 신뢰 코드를 간편하게 테스트할 수 있습니다.  신뢰할 수 없는 위치에서 가져온 코드를 실행하려면 [방법: 샌드박스에서 부분 신뢰 코드 실행](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)을 참조하십시오.  
  
-   [부분 신뢰 응용 프로그램 도메인에서 코드 실행](#Running_code).  
  
-   [부분 신뢰에서 익명으로 호스팅된 동적 메서드를 사용하여 코드 내보내기 및 실행](#Using_methods)  
  
 부분 신뢰 시나리오에서 코드를 내보내는 방법에 대한 자세한 내용은 [리플렉션 내보내기의 보안 문제점](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)을 참조하십시오.  
  
 이러한 절차에 나오는 코드의 전체 목록을 보려면 이 연습의 끝 부분에 있는 [예제](#Example) 단원을 참조하십시오.  
  
<a name="Setting_up"></a>   
## 부분 신뢰 위치 설정  
 다음 두 절차에서는 부분 신뢰 코드를 테스트할 수 있는 위치를 설정하는 방법을 보여 줍니다.  
  
-   첫 번째 절차에서는 코드에 인터넷 권한이 부여되는 샌드박싱된 응용 프로그램 도메인을 만드는 방법을 보여 주고  
  
-   두 번째 절차에서는 부분 신뢰 응용 프로그램 도메인에 <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName> 플래그가 설정된 <xref:System.Security.Permissions.ReflectionPermission>을 추가하여 같거나 낮은 신뢰 수준의 어셈블리에서 전용 데이터에 액세스할 수 있도록 하는 방법을 보여 줍니다.  
  
### 샌드박싱된 응용 프로그램 도메인 만들기  
 어셈블리가 부분 신뢰 수준으로 실행되는 응용 프로그램 도메인을 만들려면 [AppDomain.CreateDomain\(String, Evidence, AppDomainSetup, PermissionSet, StrongName\<xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=fullName> 메서드 오버로드를 사용하여 어셈블리에 부여할 권한 집합을 지정해야 합니다.  권한 부여 설정을 지정하는 가장 쉬운 방법은 보안 정책에서 명명된 권한 집합을 검색하는 것입니다.  
  
 다음 절차에서는 부분 신뢰 수준으로 코드를 실행하는 샌드박싱된 응용 프로그램 도메인을 만들어 내보낸 코드가 공용 형식의 public 멤버에만 액세스할 수 있는 시나리오를 테스트합니다.  이후 절차에서는 내보낸 코드가 같거나 낮은 권한이 부여된 어셈블리에 있는 비공용 형식과 멤버에 액세스할 수 있는 시나리오를 테스트하기 위해 <xref:System.Security.Permissions.ReflectionPermissionFlag>를 추가하는 방법을 보여 줍니다.  
  
##### 부분 신뢰가 부여된 응용 프로그램 도메인을 만들려면  
  
1.  샌드박싱된 응용 프로그램 도메인의 어셈블리에 부여할 권한 집합을 만듭니다.  이 경우 인터넷 영역의 권한 집합이 사용됩니다.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#2)]
     [!code-vb[HowToEmitCodeInPartialTrust#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#2)]  
  
2.  <xref:System.AppDomainSetup> 개체를 만들어 응용 프로그램 경로로 응용 프로그램 도메인을 초기화합니다.  
  
    > [!IMPORTANT]
    >  이 코드 예제에서는 편의상 현재 폴더를 사용합니다.  인터넷에서 가져온 코드를 실행하려면 [방법: 샌드박스에서 부분 신뢰 코드 실행](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)에 설명된 대로 별도의 폴더를 사용합니다.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#3)]
     [!code-vb[HowToEmitCodeInPartialTrust#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#3)]  
  
3.  응용 프로그램 도메인 설치 정보와 응용 프로그램 도메인에서 실행되는 모든 어셈블리에 대한 권한 부여 설정을 지정하여 응용 프로그램 도메인을 만듭니다.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#5)]
     [!code-vb[HowToEmitCodeInPartialTrust#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#5)]  
  
     [AppDomain.CreateDomain\(String, Evidence, AppDomainSetup, PermissionSet, StrongName\<xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=fullName> 메서드 오버로드의 마지막 매개 변수를 사용하면 응용 프로그램 도메인의 권한 부여 설정 대신 완전 신뢰를 부여해야 하는 어셈블리 집합을 지정할 수 있습니다.  응용 프로그램이 사용하는 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 어셈블리는 전역 어셈블리 캐시에 있으므로 지정하지 않아도 됩니다.  전역 어셈블리 캐시에 있는 어셈블리는 항상 완전히 신뢰됩니다.  이 매개 변수를 사용하여 전역 어셈블리 캐시에 없는 강력한 이름의 어셈블리를 지정할 수 있습니다.  
  
### 샌드박싱된 도메인에 RestrictedMemberAccess 추가  
 호스트 응용 프로그램에서는 익명으로 호스팅된 동적 메서드를 사용하여 코드를 내보내는 어셈블리의 신뢰 수준보다 낮거나 같은 어셈블리에 있는 전용 데이터에 액세스할 수 있습니다.  이 제한된 기능을 통해 JIT\(Just\-In\-Time\) 가시성 검사를 생략할 수 있도록 호스트 응용 프로그램은 <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName>\(RMA\) 플래그가 설정된 <xref:System.Security.Permissions.ReflectionPermission> 개체를 권한 부여 설정에 추가합니다.  
  
 예를 들어, 호스트가 인터넷 응용 프로그램에 인터넷 권한과 RMA를 부여하여 인터넷 응용 프로그램이 해당 어셈블리에 있는 전용 데이터에 액세스하는 코드를 내보낼 수 있도록 할 수 있습니다.  신뢰 수준이 같거나 낮은 어셈블리에만 액세스할 수 있기 때문에 인터넷 응용 프로그램은 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 어셈블리 같은 완전 신뢰 어셈블리의 멤버에 액세스할 수 없습니다.  
  
> [!NOTE]
>  권한 상승을 방지하기 위해 익명으로 호스팅된 동적 메서드를 생성하면 내보내는 어셈블리의 스택 정보가 포함됩니다.  이 메서드를 호출하면 스택 정보가 검사됩니다.  따라서 완전 신뢰 코드에서 호출되는 익명으로 호출된 동적 메서드는 여전히 내보내는 어셈블리의 신뢰 수준으로 제한됩니다.  
  
##### 부분 신뢰와 RMA가 부여된 응용 프로그램 도메인을 만들려면  
  
1.  <xref:System.Security.Permissions.ReflectionPermissionFlag>\(RMA\) 플래그가 설정된 새 <xref:System.Security.Permissions.ReflectionPermission> 개체를 만들고 <xref:System.Security.PermissionSet.SetPermission%2A?displayProperty=fullName> 메서드를 사용하여 권한 부여 설정에 권한을 추가합니다.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#7)]
     [!code-vb[HowToEmitCodeInPartialTrust#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#7)]  
  
     권한 부여 설정에 권한이 아직 포함되어 있지 않은 경우 <xref:System.Security.PermissionSet.AddPermission%2A> 메서드가 권한 부여 설정에 권한을 추가합니다.  권한 부여 설정에 권한이 이미 포함되어 있는 경우 지정된 플래그가 기존 권한에 추가됩니다.  
  
    > [!NOTE]
    >  RMA는 익명으로 호스팅된 동적 메서드의 기능입니다.  일반 동적 메서드가 JIT 가시성 검사를 생략할 경우 내보낸 코드에 완전 신뢰를 부여해야 합니다.  
  
2.  응용 프로그램 도메인 설치 정보 및 권한 부여 설정을 지정하여 응용 프로그램 도메인을 만듭니다.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#8)]
     [!code-vb[HowToEmitCodeInPartialTrust#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#8)]  
  
<a name="Running_code"></a>   
## 샌드박싱된 응용 프로그램 도메인에서 코드 실행  
 다음 절차에서는 응용 프로그램 도메인에서 실행할 수 있는 메서드를 사용하여 클래스를 정의하는 방법, 도메인에서 클래스의 인스턴스를 만드는 방법 및 해당 메서드를 실행하는 방법에 대해 설명합니다.  
  
#### 응용 프로그램 도메인에서 메서드를 정의하고 실행하려면  
  
1.  <xref:System.MarshalByRefObject>에서 파생되는 클래스를 정의합니다.  이렇게 하면 다른 응용 프로그램 도메인에서 클래스의 인스턴스를 만들고 응용 프로그램 도메인 경계를 넘어 메서드를 호출할 수 있습니다.  이 예제에서 클래스 이름은 `Worker`로 지정됩니다.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#10)]
     [!code-vb[HowToEmitCodeInPartialTrust#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#10)]  
  
2.  실행할 코드가 포함된 공용 메서드를 정의합니다.  이 예제에서 코드는 간단한 동적 메서드를 내보내고 메서드를 실행할 대리자를 만든 다음 대리자를 호출합니다.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#11)]
     [!code-vb[HowToEmitCodeInPartialTrust#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#11)]  
  
3.  기본 프로그램에서 어셈블리의 표시 이름을 가져옵니다.  이 이름은 샌드박싱된 응용 프로그램 도메인에서 `Worker` 클래스의 인스턴스를 만들 때 사용됩니다.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#14](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#14)]
     [!code-vb[HowToEmitCodeInPartialTrust#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#14)]  
  
4.  기본 프로그램에서 이 연습의 [첫 번째 절차](#Setting_up)에 설명된 대로 샌드박싱된 응용 프로그램 도메인을 만듭니다.  `SimpleEmitDemo` 메서드는 공용 메서드만 사용하므로 `Internet` 권한 집합에 권한을 추가할 필요는 없습니다.  
  
5.  기본 프로그램을 사용하여 샌드박싱된 응용 프로그램 도메인에서 `Worker` 클래스의 인스턴스를 만듭니다.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#12)]
     [!code-vb[HowToEmitCodeInPartialTrust#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#12)]  
  
     <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> 메서드는 대상 응용 프로그램 도메인에 개체를 만들고 이 개체의 속성과 메서드를 호출하는 데 사용할 수 있는 프록시를 반환합니다.  
  
    > [!NOTE]
    >  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 에서 이 코드를 사용 하는 경우, 네임 스페이스를 포함하도록 클래스의 이름을 변경해야 합니다.  기본적으로 네임스페이스는 프로젝트의 이름입니다.  예를 들어, 프로젝트가 "PartialTrust"이면 클래스 이름은 "PartialTrust.Worker"여야 합니다.  
  
6.  코드를 추가하여 `SimpleEmitDemo` 메서드를 호출합니다.  그러면 이 호출이 응용 프로그램 도메인 경계를 넘어 마샬링되고 코드가 샌드박싱된 응용 프로그램 도메인에서 실행됩니다.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#13)]
     [!code-vb[HowToEmitCodeInPartialTrust#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#13)]  
  
<a name="Using_methods"></a>   
## 익명으로 호스팅된 동적 메서드 사용  
 익명으로 호스팅된 동적 메서드는 시스템에서 제공하는 투명 어셈블리에 연결됩니다.  따라서 이 메서드에 포함된 코드도 투명합니다.  반면에 일반 동적 메서드는 직접 지정되거나 연결된 형식에서 유추된 기존 모듈에 연결하고 이 모듈에서 해당 보안 수준을 가져와야 합니다.  
  
> [!NOTE]
>  익명 호스팅을 제공하는 어셈블리에 동적 메서드를 연결하는 유일한 방법은 다음 절차에서 설명하는 생성자를 사용하는 것입니다.  익명 호스팅 어셈블리에서는 모듈을 명시적으로 지정할 수 있습니다.  
  
 일반 동적 메서드는 연결된 모듈의 내부 멤버나 연결된 형식의 private 멤버에 액세스할 수 있습니다.  익명으로 호스팅된 동적 메서드는 다른 코드와 격리되므로 전용 데이터에 액세스할 수 없지만  JIT 가시성 검사를 생략하는 제한된 기능이 있어 전용 데이터에 액세스할 수 있습니다.  이 기능은 코드를 내보내는 어셈블리의 신뢰 수준보다 낮거나 같은 어셈블리에서만 사용할 수 있습니다.  
  
 권한 상승을 방지하기 위해 익명으로 호스팅된 동적 메서드를 생성하면 내보내는 어셈블리의 스택 정보가 포함됩니다.  이 메서드를 호출하면 스택 정보가 검사됩니다.  따라서 완전 신뢰 코드에서 호출되는 익명으로 호출된 동적 메서드는 여전히 내보내는 어셈블리의 신뢰 수준으로 제한됩니다.  
  
#### 익명으로 호스팅된 동적 메서드를 사용하려면  
  
-   연결된 모듈이나 형식을 지정하지 않는 생성자를 사용하여 익명으로 호스팅된 동적 메서드를 만듭니다.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#15](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#15)]
     [!code-vb[HowToEmitCodeInPartialTrust#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#15)]  
  
     익명으로 호스팅된 동적 메서드가 공개 형식 및 메서드만 사용하는 경우 제한된 멤버 액세스가 필요하지 않고 JIT 가시성 검사를 생략하지 않아도 됩니다.  
  
     특별한 권한이 없어도 동적 메서드를 내보낼 수 있지만 내보낸 코드에는 사용되는 형식과 메서드에서 요구하는 권한이 필요합니다.  예를 들어, 내보낸 코드가 파일에 액세스하는 메서드를 호출하면 <xref:System.Security.Permissions.FileIOPermission>이 필요합니다.  신뢰 수준에 해당 권한이 포함되어 있지 않을 경우 내보낸 코드가 실행될 때 보안 예외가 throw됩니다.  여기에 표시된 코드는 <xref:System.Console.WriteLine%2A?displayProperty=fullName> 메서드만 사용하는 동적 메서드를 내보내기 때문에  부분 신뢰 위치에서 실행할 수 있습니다.  
  
-   또는 [DynamicMethod\(String, Type, Type\<xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%2CSystem.Boolean%29> 생성자를 사용하고 `restrictedSkipVisibility` 매개 변수에 대해 `true`를 지정하여 JIT 가시성 검사를 생략하는 제한된 기능이 있는 익명으로 호스팅된 동적 메서드를 만듭니다.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#16](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#16)]
     [!code-vb[HowToEmitCodeInPartialTrust#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#16)]  
  
     제한 사항은 익명으로 호스팅된 동적 메서드가 내보내는 어셈블리의 신뢰 수준보다 낮거나 같은 어셈블리에서만 전용 데이터에 액세스할 수 있다는 점입니다.  예를 들어, 동적 메서드를 인터넷 신뢰 수준으로 실행하는 경우 마찬가지로 인터넷 신뢰 수준으로 실행되는 어셈블리의 전용 데이터에는 액세스할 수 있지만 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 어셈블리의 전용 데이터에는 액세스할 수 없습니다.  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 어셈블리는 전역 어셈블리 캐시에 설치되고 항상 완전히 신뢰됩니다.  
  
     호스트 응용 프로그램이 <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName> 플래그가 설정된 <xref:System.Security.Permissions.ReflectionPermission>을 부여하는 경우에만 익명으로 호스팅된 동적 메서드는 이 제한된 기능을 사용하여 JIT 가시성 검사를 생략할 수 있습니다.  이 권한은 메서드를 호출할 때 요청됩니다.  
  
    > [!NOTE]
    >  동적 메서드를 생성하면 내보내는 어셈블리에 대한 호출 스택 정보가 포함됩니다.  따라서 메서드를 호출하는 어셈블리가 아니라 내보내는 어셈블리의 권한이 요청됩니다.  이것은 내보낸 코드가 더 높은 권한으로 실행되는 것을 방지합니다.  
  
     이 연습의 끝 부분에 있는 [전체 코드 예제](#Example)에서는 제한된 멤버 액세스의 사용과 제한 사항을 보여 줍니다.  해당 `Worker` 클래스에는 가시성 검사를 생략하는 제한된 기능이 포함 또는 포함되지 않는 익명으로 호스팅된 동적 메서드를 만들 수 있는 메서드가 포함되어 있고, 예제에서는 신뢰 수준이 다른 응용 프로그램 도메인에서 이 메서드를 실행할 경우의 결과를 보여 줍니다.  
  
    > [!NOTE]
    >  가시성 검사를 생략하는 제한된 기능은 익명으로 호스팅된 동적 메서드의 기능입니다.  일반 동적 메서드가 JIT 가시성 검사를 생략할 경우 해당 메서드에 완전 신뢰를 부여해야 합니다.  
  
<a name="Example"></a>   
## 예제  
  
### 설명  
 다음 코드 예제에서는 <xref:System.Security.Permissions.ReflectionPermissionFlag> 플래그를 사용하여 익명으로 호스팅된 동적 메서드의 JIT 가시성 검사를 생략하는 방법을 보여 줍니다. 이렇게 하려면 대상 멤버의 신뢰 수준이 코드를 내보내는 어셈블리의 신뢰 수준보다 낮거나 같아야 합니다.  
  
 이 예제에서는 응용 프로그램 도메인 경계를 넘어 마샬링할 수 있는 `Worker` 클래스를 정의합니다.  이 클래스에는 동적 메서드를 내보내고 실행하는 두 개의 `AccessPrivateMethod` 메서드 오버로드가 있습니다.  첫 번째 오버로드는 `Worker` 클래스의 `PrivateMethod` 메서드를 호출하는 동적 메서드를 내보냅니다. 이 오버로드에서 동적 메서드를 내보낼 때 JIT 가시성 검사를 수행하거나 생략할 수 있습니다.  두 번째 오버로드는 <xref:System.String> 클래스의 `internal` 속성\(Visual Basic의 경우 `Friend` 속성\)에 액세스하는 동적 메서드를 내보냅니다.  
  
 이 예제에서는 도우미 메서드를 사용하여 `Internet`으로 제한된 권한 부여 설정을 만든 다음 도메인에서 실행되는 모든 코드에 이 권한 부여 설정이 사용되도록 지정하는 [AppDomain.CreateDomain\(String, Evidence, AppDomainSetup, PermissionSet, StrongName\<xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=fullName> 메서드 오버로드를 사용하여 응용 프로그램 도메인을 만듭니다.  이 예제에서는 응용 프로그램 도메인에 `Worker` 클래스의 인스턴스를 만들고 `AccessPrivateMethod` 메서드를 두 번 실행합니다.  
  
-   `AccessPrivateMethod` 메서드를 처음 실행하면 JIT 가시성 검사가 수행됩니다.  JIT 가시성 검사에서는 동적 메서드가 private 메서드에 액세스하지 못하도록 차단하므로 동적 메서드를 호출할 때 작업이 실패합니다.  
  
-   `AccessPrivateMethod` 메서드를 두 번째로 실행할 때는 JIT 가시성 검사가 생략됩니다.  `Internet` 권한 부여 설정에서는 가시성 검사를 생략하기에 충분한 권한을 부여하지 않으므로 동적 메서드를 컴파일할 때 작업이 실패합니다.  
  
 다음 예제에서는 권한 부여 설정에 <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName>가 설정된 <xref:System.Security.Permissions.ReflectionPermission>을 추가합니다.  그런 다음 도메인에서 실행되는 모든 코드에 새 부여 집합의 권한을 부여하도록 지정하여 두 번째 도메인을 만듭니다.  이 예제에서는 새 응용 프로그램 도메인에 `Worker` 클래스의 인스턴스를 만들고 `AccessPrivateMethod` 메서드의 두 오버로드를 모두 실행합니다.  
  
-   `AccessPrivateMethod` 메서드의 첫 번째 오버로드를 실행할 때는 JIT 가시성 검사가 생략됩니다.  코드를 내보내는 어셈블리가 private 메서드를 포함하는 어셈블리와 같으므로 동적 메서드가 성공적으로 컴파일되고 실행됩니다.  따라서 신뢰 수준이 동일합니다.  `Worker` 클래스를 포함하는 응용 프로그램에 여러 어셈블리가 있으면 각 어셈블리의 신뢰 수준이 모두 같으므로 동일한 프로세스가 해당 어셈블리 각각에 대해 성공합니다.  
  
-   `AccessPrivateMethod` 메서드의 두 번째 오버로드를 실행할 때에도 JIT 가시성 검사가 생략됩니다.  그러나 이번에는 해당 메서드에서 <xref:System.String> 클래스의 `internal` `FirstChar` 속성에 액세스하므로 동적 메서드를 컴파일할 때 작업이 실패합니다.  <xref:System.String> 클래스가 들어 있는 어셈블리는 완전히 신뢰되므로  코드를 내보내는 어셈블리보다 신뢰 수준이 높습니다.  
  
 이러한 비교를 통해 부분 신뢰 코드에서 <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName>를 사용하여 신뢰 코드의 보안에 악영향을 주지 않고 다른 부분 신뢰 코드에 대한 가시성 검사를 생략하는 방법을 확인할 수 있습니다.  
  
### 코드  
 [!code-csharp[HowToEmitCodeInPartialTrust#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#1)]
 [!code-vb[HowToEmitCodeInPartialTrust#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#1)]  
  
## 코드 컴파일  
  
-   [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 이 코드 예제를 빌드하는 경우에는 클래스를 <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> 메서드에 전달할 때 네임스페이스를 포함하도록 클래스의 이름을 변경해야 합니다.  기본적으로 네임스페이스는 프로젝트의 이름입니다.  예를 들어, 프로젝트가 "PartialTrust"이면 클래스 이름은 "PartialTrust.Worker"여야 합니다.  
  
## 참고 항목  
 [리플렉션 내보내기의 보안 문제점](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)   
 [방법: 샌드박스에서 부분 신뢰 코드 실행](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)