---
title: "보안 및 경합 상태"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 73664df9c072189f11d451da46bc3019c8593ec9
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="security-and-race-conditions"></a>보안 및 경합 상태
중요 한 보안 허점 경합 상태에 의해 악용 가능성이 시킵니다. 여러 가지 방법으로이 발생할 수 있습니다. 다음에 나오는 하위 개발자 피해 야 하는 주요 문제 중 일부를 간략하게 설명 합니다.  
  
## <a name="race-conditions-in-the-dispose-method"></a>Dispose 메서드에서 경합 상태  
 클래스의 경우 **Dispose** 메서드 (자세한 내용은 참조 [가비지 수집](../../../docs/standard/garbage-collection/index.md))은 동기화 되지 않을 수도 있기 내부 정리 코드 **Dispose** 실행 될 수 있습니다 이상 한 번, 다음 예제와 같이 합니다.  
  
```vb  
Sub Dispose()  
    If Not (myObj Is Nothing) Then  
       Cleanup(myObj)  
       myObj = Nothing  
    End If  
End Sub  
```  
  
```csharp  
void Dispose()   
{  
    if( myObj != null )   
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 때문에이 **Dispose** 구현은 동기화 되지 않으면는 `Cleanup` 첫 번째 스레드 및 하기 전에 두 번째 스레드가 호출 될 `_myObj` 로 설정 된 **null**합니다. 수행 되는 작업에 따라 달라 집니다이 보안 문제 인지 때는 `Cleanup` 코드를 실행 합니다. 와 동기화 되지 않은 중요 한 문제 **Dispose** 구현 파일 같은 리소스 핸들의 사용이 포함 됩니다. 메서드를 잘못 하면 잘못 된 핸들이 사용할 수 있으며이 보안 취약점으로 인해 발생할 수 있습니다.  
  
## <a name="race-conditions-in-constructors"></a>생성자의 경합 상태  
 일부 응용 프로그램에서 다른 스레드를 클래스 생성자가 완전히 실행 하기 전에 클래스 멤버에 액세스할 수 있습니다. 이 발생 하거나 필요한 경우 스레드를 동기화 해야 하는 경우 보안 문제가 없는지를 확인 하기 위해 모든 클래스 생성자를 검토 해야 합니다.  
  
## <a name="race-conditions-with-cached-objects"></a>캐시 된 개체와 경합 상태  
 보안 정보를 캐시 하거나 코드 액세스 보안을 사용 하는 코드 [Assert](../../../docs/framework/misc/using-the-assert-method.md) 작업이 노출 될 수 있습니다 경합 상태에는 클래스의 다른 부분 적절 하 게 동기화 되지 않은 경우 다음 예제와 같이 합니다.  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False()  
    End If  
End Sub  
  
Sub DoOtherWork()  
    If fCallersOK Then  
        DoSomethingTrusted()  
    Else  
        DemandSomething()  
        DoSomethingTrusted()  
    End If  
End Sub  
```  
  
```csharp  
void SomeSecureFunction()   
{  
    if(SomeDemandPasses())   
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false();  
    }  
}  
void DoOtherWork()   
{  
    if( fCallersOK )   
    {  
        DoSomethingTrusted();  
    }  
    else   
    {  
        DemandSomething();  
        DoSomethingTrusted();  
    }  
}  
```  
  
 다른 경로가 있으면 `DoOtherWork` 같은 개체와 다른 스레드에서 호출할 수 있는, 요청을 지 나 신뢰할 수 없는 호출자 지연 될 수 있습니다.  
  
 코드 보안 정보를 캐시 하는 경우이 취약점에 대 한 검토 해야 합니다.  
  
## <a name="race-conditions-in-finalizers"></a>종료자의 경합 상태  
 경합 상태 종료자에서 해제 하는 정적 또는 관리 되지 않는 리소스를 참조 하는 개체에도 발생할 수 있습니다. 여러 개체 클래스의 종료자에서 조작 되는 리소스를 공유 하는 경우 개체에 해당 리소스에 대 한 모든 액세스를 동기화 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [보안 코딩 지침](../../../docs/standard/security/secure-coding-guidelines.md)
