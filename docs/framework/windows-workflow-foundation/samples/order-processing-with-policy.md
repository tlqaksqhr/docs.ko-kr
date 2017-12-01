---
title: "정책을 사용한 주문 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66833724-dc36-4fad-86b0-59ffeaa3ba6a
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6202d17741c276c03e80cedd979cbcf2f39ccc1f
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="order-processing-with-policy"></a>정책을 사용한 주문 처리
Order Processing Policy 샘플에서는 Windows WF(Workflow Foundation )의 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]에 도입된 몇 가지 주요 기능을 보여 줍니다. 다음은 WF 규칙 엔진에 새로 추가된 기능입니다.  
  
-   연산자 오버로드 지원  
  
-   사용자가 WF 규칙에서 새 개체 및 배열을 만들 수 있는 `new` 연산자 지원  
  
-   C# 코딩 스타일과 호환되는 WF 규칙에서 확장 메서드를 호출할 때 사용자 환경을 만드는 확장 메서드 지원  
  
> [!NOTE]
>  이 샘플을 실행하려면 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]가 설치되어 빌드 및 실행되어야 합니다. 프로젝트 및 솔루션 파일을 열려면 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]이 필요합니다.  
  
 이 샘플에서는 번호가 매겨진 사용 가능한 항목 목록으로 구성된 고객 주문과 우편 번호를 입력하는 `OrderProcessingPolicy` 프로젝트를 보여 줍니다. 두 항목이 모두 올바르면 주문이 성공적으로 처리되고, 그렇지 않으면 정책에서 오버로드된 `+` 연산자와 미리 정의된 확장 메서드를 사용하여 사용자에게 오류를 알리는 오류 개체를 만듭니다.  
  
> [!NOTE]
>  [!INCLUDE[crabout](../../../../includes/crabout-md.md)]확장 메서드 참조 [C# 버전 3.0 사양](http://go.microsoft.com/fwlink/?LinkId=95402)합니다.  
  
 이 샘플은 다음과 같은 프로젝트로 구성됩니다.  
  
-   `OrderErrorLibrary`  
  
     `OrderErrorLibrary`는 `OrderError` 및 `OrderErrorCollection` 클래스를 정의하는 클래스 라이브러리입니다. `OrderError` 인스턴스는 잘못된 입력을 제공할 때 만들어집니다. 또한 이 라이브러리는 `OrderErrorCollection`의 모든 `ErrorText` 개체에 대해 `OrderError` 속성을 출력하는 `OrderErrorCollection` 클래스에서 확장 메서드를 제공합니다.  
  
-   `OrderProcessingPolicy`  
  
     `OrderProcessingPolicy` 프로젝트는 단일 `PolicyFromFile` 활동을 정의하는 WF 콘솔 응용 프로그램입니다. 활동에는 다음과 같은 규칙이 있습니다.  
  
    -   `invalidItemNum`  
  
         이 규칙은 항목 번호가 1에서 6 사이에 있는지를 확인합니다. 항목 번호가 유효한 범위 내에 있으면 규칙에서 아무 작업도 수행하지 않고 콘솔에 출력만 합니다. 항목 번호가 1에서 6 사이에 없으면 `invalidItemNum` 규칙에서 다음 작업을 수행합니다.  
  
        1.  새 `OrderError` 개체를 만들어 입력된 항목 번호를 전달하고 개체에서 `ErrorText` 및 `CustomerName` 속성을 설정합니다.  
  
        2.  `invalidItemNumErrorCollection` 개체를 만듭니다.  
  
        3.  새로 만든 `OrderError` 인스턴스를 `invalidItemNumErrorCollection`에 추가합니다.  
  
         이 규칙은 규칙 내에서 개체를 인스턴스화하는 데 사용할 수 있는 `new` 연산자에 대한 지원을 보여 줍니다.  
  
    -   `invalidZip`  
  
         이 규칙은 우편 번호가 5자리이며 600에서 99998 사이의 범위 내에 있는지 확인합니다. 우편 번호가 유효한 범위 내에 있으면 규칙에서 아무 작업도 수행하지 않고 콘솔에 출력만 합니다. 우편 번호의 길이가 5보다 작거나 00600에서 99998 사이에 없으면 `invalidZip` 규칙에서 다음 작업을 수행합니다.  
  
        1.  `OrderError` 개체를 만들어 입력된 우편 번호를 전달하고 개체에서 `ErrorText` 및 `CustomerName` 속성을 설정합니다.  
  
        2.  `invalidZipCodeErrorCollection` 개체를 만듭니다.  
  
        3.  새로 만든 `OrderError` 인스턴스를 새로 만든 `invalidZipCodeErrorCollection`에 추가합니다.  
  
         이 규칙도 규칙 내에서 개체를 인스턴스화하는 데 사용할 수 있는 `new` 연산자에 대한 지원을 보여 줍니다.  
  
    -   `displayErrors`  
  
         이 규칙은 앞의 두 규칙에 의해 두 `OrderErrorCollection` 개체인 `invalidItemNumErrorCollection`과 `invalidIZipCodeErrorCollection`에 추가된 오류가 있는지 확인합니다. 오류가 있는 경우(`invalidItemNumErrorCollection` 또는 `invalidZipCodeErrorCollection`이 `null`이 아닌 경우) 규칙에서 다음 작업을 수행합니다.  
  
        1.  호출 하는 오버 로드 된 `+` 연산자의 내용을 복사를 `invalidItemNumErrorCollection` 및 `invalidZipCodeErrorCollection` 에 `invalidOrdersCollection``OrderErrorCollection` 인스턴스.  
  
        2.  `PrintOrderErrors`에서 `invalidOrdersCollection` 확장 메서드를 호출하고 `ErrorText`의 모든 `orderError` 개체에서 `invalidOrdersCollection` 속성을 출력합니다.  
  
 `+`의 오버로드된 `OrderErrorCollection` 연산자는 `OrderErrorCollection` 프로젝트의 `OrderErrorLibrary` 클래스에 정의되어 있습니다. 이 연산자는 두 개의 `OrderErrorCollection` 개체를 사용하여 하나의 `OrderErrorCollection` 개체로 결합합니다.  
  
 `PrintOrderErrors` 확장 메서드도 `OrderErrorLibrary` 프로젝트에 정의되어 있습니다. 확장 메서드는 개발자가 클래스를 파생하거나 원래 형식을 다시 컴파일하지 않고도 기존 CLR 형식의 공용 계약에 새 메서드를 추가할 수 있는 새로운 C# 기능입니다.  
  
 샘플을 실행하면 이름, 구입할 항목의 항목 번호 및 우편 번호를 입력하라는 메시지가 나타납니다. 그런 다음 정책 활동에 정의된 규칙에서 이 정보를 확인합니다. 다음은 프로그램의 출력 샘플입니다.  
  
```  
Please enter your name: John  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 1  
  
Please enter your 5-Digit zip code: 98102  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Thank you for your order, it has been processed.  
  
Workflow Completed  
Another Order? (Y/N): y  
  
Please enter your name: Joel  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 8  
  
Please enter your 5-Digit zip code: 0000  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Your order contains the following error(s)  
  
Error: No item number found. Please choose an available item.  
Error: Invalid zip code. Please choose a zip code between 00600 and 99998.  
  
Workflow Completed  
Another Order? (Y/N): n  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 OrderProcessingPolicy.sln 프로젝트 파일을 엽니다.  
  
2.  솔루션에는 `OrderErrorLibrary` 및 `OrderProcessingPolicy`라는 두 개의 다른 프로젝트가 있습니다. `OrderProcessingPolicy` 프로젝트에서는 `OrderErrorLibrary`에 정의된 클래스 및 메서드를 사용합니다.  
  
3.  프로젝트를 모두 빌드합니다.  
  
4.  **실행**을 클릭합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\OrderProcessingPolicy`