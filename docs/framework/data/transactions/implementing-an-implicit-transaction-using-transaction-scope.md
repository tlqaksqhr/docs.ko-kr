---
title: "트랜잭션 범위를 사용하여 암시적 트랜잭션 구현  | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49d1706a-1e0c-4c85-9704-75c908372eb9
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 트랜잭션 범위를 사용하여 암시적 트랜잭션 구현 
<xref:System.Transactions.TransactionScope> 클래스는 트랜잭션 자체와 상호 작용할 필요 없이 코드 블록을 트랜잭션에 참여하는 것으로 표시하는 단순한 방법을 제공합니다.트랜잭션 범위는 자동으로 앰비언트 트랜잭션을 선택하고 관리할 수 있습니다.사용하기 쉽고 효율적이므로 트랜잭션 응용 프로그램을 개발할 때는 <xref:System.Transactions.TransactionScope> 클래스를 사용하는 것이 좋습니다.  
  
 또한 트랜잭션을 사용하여 명시적으로 리소스를 등록할 필요가 없습니다.<xref:System.Transactions> 리소스 관리자\(예: SQL Server 2005\)는 범위에서 만든 앰비언트 트랜잭션이 있는지 감지하고 자동으로 등록할 수 있습니다.  
  
## 트랜잭션 범위 만들기  
 다음 샘플에서는 <xref:System.Transactions.TransactionScope> 클래스의 단순한 사용을 보여 줍니다.  
  
 [!code-csharp[TransactionScope#1](../../../../samples/snippets/csharp/VS_Snippets_Remoting/TransactionScope/cs/ScopeWithSQL.cs#1)]
 [!code-vb[TransactionScope#1](../../../../samples/snippets/visualbasic/VS_Snippets_Remoting/TransactionScope/vb/ScopeWithSQL.vb#1)]  
  
 새 <xref:System.Transactions.TransactionScope> 개체를 만들면 트랜잭션 범위가 시작됩니다. **using** 문으로 범위를 만드는 것이 좋습니다.**using** 문은 C\# 및 Visual Basic에서 모두 사용할 수 있으며 **try...finally** 블록처럼 작동하여 범위가 제대로 삭제되게 합니다.  
  
 <xref:System.Transactions.TransactionScope>를 시작하면 트랜잭션 관리자는 참가할 트랜잭션을 결정합니다.일단 결정되면 범위는 항상 해당 트랜잭션에 참여합니다.앰비언트 트랜잭션이 있는지 여부와 생성자에 있는 **TransactionScopeOption** 매개 변수의 값에 따라 참여할 트랜잭션이 결정됩니다.앰비언트 트랜잭션은 코드가 실행되는 트랜잭션입니다.<xref:System.Transactions.Transaction> 클래스의 정적 <xref:System.Transactions.Transaction.Current%2A> 속성을 호출하여 앰비언트 트랜잭션에 대한 참조를 가져올 수 있습니다.이 매개 변수를 사용하는 방법에 대한 자세한 내용은 이 항목의 TransactionScopeOption을 사용하여 트랜잭션 흐름 관리 섹션을 참조하십시오.  
  
## 트랜잭션 범위 완료  
 응용 프로그램이 트랜잭션에서 수행할 작업을 모두 완료하면 <xref:System.Transactions.TransactionScope.Complete%2A> 메서드를 한 번만 호출하여 트랜잭션 커밋이 허용됨을 트랜잭션 관리자에게 알려야 합니다.<xref:System.Transactions.TransactionScope.Complete%2A> 호출을 **using** 블록의 마지막 문으로 배치하는 것이 좋습니다.  
  
 이 메서드를 호출하지 못하면 트랜잭션 관리자가 이 오류를 시스템 오류나 트랜잭션 범위에서 throw된 예외와 동등한 것으로 해석하기 때문에 트랜잭션이 중단됩니다.그러나 이 메서드를 호출해도 반드시 트랜잭션이 커밋되지는 않습니다.이 메서드를 호출하는 것은 트랜잭션 관리자에게 상태를 알리는 수단일 뿐입니다.<xref:System.Transactions.TransactionScope.Complete%2A> 메서드를 호출한 후에는 더 이상 <xref:System.Transactions.Transaction.Current%2A> 속성을 통해 앰비언트 트랜잭션에 액세스할 수 없으며 액세스를 시도하면 예외가 throw됩니다.  
  
 <xref:System.Transactions.TransactionScope> 개체가 처음으로 트랜잭션을 만든 경우 실제로 트랜잭션 관리자가 트랜잭션을 커밋하는 작업은 **using** 블록의 마지막 코드 줄 이후에 발생합니다.트랜잭션을 만들지 않은 경우 <xref:System.Transactions.CommittableTransaction> 개체 소유자가 <xref:System.Transactions.CommittableTransaction.Commit%2A>을 호출할 때마다 커밋이 발생합니다.이때 트랜잭션 관리자가 리소스 관리자를 호출하여 <xref:System.Transactions.TransactionScope> 개체에서 <xref:System.Transactions.TransactionScope.Complete%2A> 메서드가 호출되었는지 여부에 따라 커밋하거나 롤백하도록 알립니다.  
  
 **using** 문은 예외가 발생하는 경우에도 <xref:System.Transactions.TransactionScope> 개체의 <xref:System.Transactions.TransactionScope.Dispose%2A> 메서드가 호출되도록 합니다.<xref:System.Transactions.TransactionScope.Dispose%2A> 메서드는 트랜잭션 범위의 끝을 표시합니다.이 메서드를 호출한 후에 발생하는 예외는 트랜잭션에 영향을 주지 않습니다.또한 이 메서드는 앰비언트 트랜잭션을 이전 상태로 복원합니다.  
  
 범위가 트랜잭션을 만들면 <xref:System.Transactions.TransactionAbortedException>이 throw되고 트랜잭션이 중단됩니다.트랜잭션 관리자가 커밋 결정에 도달할 수 없는 경우 <xref:System.Transactions.TransactionIndoubtException>이 throw됩니다.트랜잭션이 커밋되면 예외가 throw되지 않습니다.  
  
## 트랜잭션 롤백  
 트랜잭션을 롤백하려면 트랜잭션 범위 내에서 <xref:System.Transactions.TransactionScope.Complete%2A> 메서드를 호출하면 안 됩니다.예를 들어 범위 내에서 예외를 throw할 수 있습니다.범위가 참여하는 트랜잭션이 롤백됩니다.  
  
##  <a name="ManageTxFlow"></a> TransactionScopeOption을 사용하여 트랜잭션 흐름 관리  
 다음 예제의 `RootMethod` 메서드와 같이 자체 범위를 사용하는 메서드 내의 <xref:System.Transactions.TransactionScope>를 사용하는 메서드를 호출하여 트랜잭션 범위를 중첩할 수 있습니다.  
  
```csharp  
void RootMethod()  
{  
     using(TransactionScope scope = new TransactionScope())  
     {  
          /* Perform transactional work here */  
          SomeMethod();  
          scope.Complete();  
     }  
}  
  
void SomeMethod()  
{  
     using(TransactionScope scope = new TransactionScope())  
     {  
          /* Perform transactional work here */  
          scope.Complete();  
     }  
}  
```  
  
 맨 위의 트랜잭션 범위를 루트 범위라고 합니다.  
  
 <xref:System.Transactions.TransactionScope> 클래스는 범위의 트랜잭션 동작을 정의하는 <xref:System.Transactions.TransactionScopeOption> 형식의 열거를 받아들이는 여러 개의 오버로드된 생성자를 제공합니다.  
  
 <xref:System.Transactions.TransactionScope> 개체에는 다음 세 가지 옵션이 있습니다.  
  
-   앰비언트 트랜잭션에 참여하거나 앰비언트 트랜잭션이 없는 경우 새로 만듭니다.  
  
-   새 루트 범위로 설정합니다. 즉, 새 트랜잭션을 시작하고 해당 트랜잭션이 자체 범위 내부의 새 앰비언트 트랜잭션이 되도록 합니다.  
  
-   트랜잭션에 참여하지 않습니다.이렇게 하면 앰비언트 트랜잭션이 없습니다.  
  
 <xref:System.Transactions.TransactionScopeOption>를 사용하여 범위를 인스턴스화하고 앰비언트 트랜잭션이 있는 경우 범위가 해당 트랜잭션에 참여합니다.반면 앰비언트 트랜잭션이 없으면 범위가 새 트랜잭션을 만들고 루트 범위가 됩니다.이 값이 기본값입니다.<xref:System.Transactions.TransactionScopeOption>를 사용하는 경우 루트이든 앰비언트 트랜잭션에 참여하든 관계없이 범위 내부의 코드가 다르게 동작할 필요가 없습니다.두 경우에서 모두 동일하게 작동해야 합니다.  
  
 <xref:System.Transactions.TransactionScopeOption>를 사용하여 범위를 인스턴스화하는 경우 항상 루트 범위가 됩니다.새 트랜잭션을 시작하고 해당 트랜잭션이 범위 내부의 새 앰비언트 트랜잭션이 됩니다.  
  
 <xref:System.Transactions.TransactionScopeOption>를 사용하여 범위를 인스턴스화하는 경우 앰비언트 트랜잭션이 있는지 여부에 관계없이 트랜잭션에 참여하지 않습니다.이 값으로 인스턴스화된 범위는 항상 **null**을 앰비언트 트랜잭션으로 사용합니다.  
  
 위의 옵션은 다음 표에 요약되어 있습니다.  
  
|TransactionScopeOption|앰비언트 트랜잭션|범위의 참여 여부|  
|----------------------------|---------------|---------------|  
|Required|아니요|새 트랜잭션\(루트가 됨\)|  
|RequiresNew|아니요|새 트랜잭션\(루트가 됨\)|  
|Suppress|아니요|트랜잭션 없음|  
|Required|예|앰비언트 트랜잭션|  
|RequiresNew|예|새 트랜잭션\(루트가 됨\)|  
|Suppress|예|트랜잭션 없음|  
  
 <xref:System.Transactions.TransactionScope> 개체가 기존의 앰비언트 트랜잭션에 참여하는 경우 범위가 트랜잭션을 중단하지 않으면 범위 개체를 삭제해도 트랜잭션이 종료되지 않을 수 있습니다.루트 범위로 앰비언트 트랜잭션을 만든 경우 루트 범위가 삭제되는 경우에만 트랜잭션에서 <xref:System.Transactions.CommittableTransaction.Commit%2A>이 호출됩니다.수동으로 트랜잭션을 만든 경우 작성자가 트랜잭션을 중단하거나 커밋할 때 트랜잭션이 종료됩니다.  
  
 다음 예제에서는 각각 다른 <xref:System.Transactions.TransactionScopeOption> 값으로 인스턴스화된 세 가지 중첩 범위 개체를 만드는 <xref:System.Transactions.TransactionScope> 개체를 보여 줍니다.  
  
```csharp  
using(TransactionScope scope1 = new TransactionScope())   
//Default is Required   
{   
     using(TransactionScope scope2 = new   
      TransactionScope(TransactionScopeOption.Required))   
     {  
     ...  
     }   
  
     using(TransactionScope scope3 = new TransactionScope(TransactionScopeOption.RequiresNew))   
     {  
     ...  
     }   
  
     using(TransactionScope scope4 = new   
        TransactionScope(TransactionScopeOption.Suppress))   
    {  
     ...  
    }   
}  
```  
  
 이 예제에서는 <xref:System.Transactions.TransactionScopeOption>를 사용하여 새 범위\(`scope1`\)를 만드는 앰비언트 트랜잭션이 없는 코드 블록을 보여 줍니다.`scope1` 범위는 새 트랜잭션\(Transaction A\)을 만들 때 루트 범위이며 Transaction A를 앰비언트 트랜잭션으로 설정합니다.그런 다음 `Scope1`은 각각 다른 <xref:System.Transactions.TransactionScopeOption> 값을 사용하여 세 개의 개체를 추가로 만듭니다.예를 들어 `scope2`는 <xref:System.Transactions.TransactionScopeOption>를 사용하여 만들어지고 앰비언트 트랜잭션이 있으므로 `scope1`에서 만든 첫 번째 트랜잭션에 참여합니다.`scope3`은 새 트랜잭션의 루트 범위이고 `scope4`에는 앰비언트 트랜잭션이 없습니다.  
  
 <xref:System.Transactions.TransactionScopeOption>의 기본값이며 가장 일반적으로 사용되는 값은 <xref:System.Transactions.TransactionScopeOption>이고 다른 값은 각각 고유한 용도를 가집니다.  
  
 <xref:System.Transactions.TransactionScopeOption>는 코드 섹션에서 수행한 작업을 유지하고 작업이 실패해도 앰비언트 트랜잭션을 중단하지 않으려는 경우에 유용합니다.예를 들어 로깅 또는 감사 작업을 수행하려는 경우 또는 앰비언트 트랜잭션이 커밋 또는 중단되든 관계없이 구독자에게 이벤트를 게시하려는 경우에 유용합니다.이 값을 사용하면 다음 예제와 같이 트랜잭션 범위 내부에 비트랜잭션 코드 섹션이 있을 수 있습니다.  
  
```csharp  
using(TransactionScope scope1 = new TransactionScope())  
{  
     try  
     {  
          //Start of non-transactional section   
          using(TransactionScope scope2 = new  
             TransactionScope(TransactionScopeOption.Suppress))  
          {  
               //Do non-transactional work here  
          }  
          //Restores ambient transaction here  
   }  
     catch  
     {}  
   //Rest of scope1  
}  
  
```  
  
### 중첩된 범위 내부의 응답  
 중첩된 범위는 루트 범위의 앰비언트 트랜잭션에 참여할 수 있지만 중첩된 범위에서 <xref:System.Transactions.TransactionScope.Complete%2A>를 호출하면 루트 범위에 영향을 주지 않습니다.루트 범위에서 마지막 중첩 범위까지의 모든 범위가 트랜잭션을 커밋하도록 응답하는 경우에만 트랜잭션이 커밋됩니다.중첩된 범위에서 <xref:System.Transactions.TransactionScope.Complete%2A>를 호출하지 않으면 앰비언트 트랜잭션이 즉시 중단되므로 루트 범위에 영향을 미칩니다.  
  
## TransactionScope 시간 제한 설정  
 <xref:System.Transactions.TransactionScope>의 오버로드된 생성자 중 일부는 트랜잭션의 시간 제한을 제어하는 데 사용되는 <xref:System.TimeSpan> 형식의 값을 받아들입니다.시간 제한을 0으로 설정하면 시간 제한이 없음을 의미합니다.무한 시간 제한은 대체로 코드를 단계별로 실행하여 비즈니스 논리의 문제를 격리하고 문제를 찾는 동안 디버그가 시간 초과되지 않도록 하려는 경우 디버깅에 유용합니다.무한 시간 제한 값은 트랜잭션 교착 상태에 대한 안전 장치를 재정의하므로 다른 모든 경우에서는 사용 시 주의해야 합니다.  
  
 일반적으로 두 가지 경우에서 <xref:System.Transactions.TransactionScope> 시간 제한을 기본값이 아닌 값으로 설정합니다.첫 번째는 개발 중으로, 응용 프로그램이 중단된 트랜잭션을 처리하는 방법을 테스트하려는 경우입니다.시간 제한을 더 작은 값\(예: 1밀리초\)으로 설정하여 트랜잭션이 실패하게 하고 오류 처리 코드를 확인할 수 있습니다.이 값을 기본 시간 제한보다 작은 값으로 설정하는 두 번째 경우는 범위가 리소스 충돌과 관련되어 교착 상태가 발생한다고 생각하는 경우입니다.이 경우 가능한 한 빨리 트랜잭션을 중단하고 기본 시간 제한이 만료될 때까지 기다리지 않으려고 합니다.  
  
 범위가 앰비언트 트랜잭션에 참여하지만 앰비언트 트랜잭션이 설정된 시간 제한보다 작은 시간 제한을 지정하는 경우 <xref:System.Transactions.TransactionScope> 개체에 더 짧은 새 시간 제한이 적용되고 범위가 지정된 중첩 시간 내에 종료되어야 합니다. 그렇지 않으면 트랜잭션이 자동으로 중단됩니다.중첩된 범위의 시간 제한이 앰비언트 트랜잭션의 시간 제한보다 크면 영향을 주지 않습니다.  
  
## TransactionScope 격리 수준 설정  
 <xref:System.Transactions.TransactionScope>의 오버로드된 생성자 중 일부는 <xref:System.Transactions.TransactionOptions> 형식의 구조를 받아들여 시간 제한 값 외에 격리 수준을 지정합니다.기본적으로 트랜잭션은 격리 수준을 <xref:System.Transactions.IsolationLevel>로 설정하여 실행됩니다.<xref:System.Transactions.IsolationLevel>이 아닌 격리 수준 선택은 일반적으로 읽기를 주로 사용하는 시스템에 사용됩니다.이 경우 트랜잭션 처리 이론과 트랜잭션 자체의 의미 체계, 관련된 동시성 문제, 시스템 일관성에 대한 영향을 이해해야 합니다.  
  
 또한 모든 리소스 관리자가 모든 격리 수준을 지원하지는 않으며, 구성된 수준보다 더 높은 수준의 트랜잭션에 참여하도록 선택할 수 있습니다.  
  
 <xref:System.Transactions.IsolationLevel> 외의 모든 격리 수준에서 동일한 정보에 액세스하는 다른 트랜잭션으로 인한 불일치가 발생할 수 있습니다.각 격리 수준의 차이점은 읽기 및 쓰기 잠금의 사용 방식입니다.트랜잭션이 리소스 관리자의 데이터에 액세스할 때만 잠금을 유지하거나 트랜잭션이 커밋 또는 중단될 때까지 유지할 수 있습니다.전자는 처리량 향상에 효과적이고 후자는 일관성 유지에 효과적입니다.두 종류의 잠금과 두 종류의 작업\(읽기\/쓰기\)으로 네 가지 기본 격리 수준이 만들어집니다.자세한 내용은 <xref:System.Transactions.IsolationLevel>을 참조하십시오.  
  
 중첩된 <xref:System.Transactions.TransactionScope> 개체를 사용하는 경우 모든 중첩 범위가 앰비언트 트랜잭션에 참여하려면 동일한 격리 수준을 사용하도록 구성해야 합니다.중첩된 <xref:System.Transactions.TransactionScope> 개체가 앰비언트 트랜잭션에 참여하려고 하지만 다른 격리 수준을 지정하는 경우 <xref:System.ArgumentException>이 throw됩니다.  
  
## COM\+와의 상호 운용성  
 새 <xref:System.Transactions.TransactionScope> 인스턴스를 만드는 경우 생성자 중 하나에 <xref:System.Transactions.EnterpriseServicesInteropOption> 열거를 사용하여 COM\+와 상호 작용하는 방법을 지정할 수 있습니다.이에 대한 자세한 내용은 [엔터프라이즈 서비스 및 COM\+ 트랜잭션과의 상호 운용성 ](../../../../docs/framework/data/transactions/interoperability-with-enterprise-services-and-com-transactions.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Transactions.Transaction.Clone%2A>   
 <xref:System.Transactions.TransactionScope>