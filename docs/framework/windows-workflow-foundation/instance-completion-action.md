---
title: "인스턴스 완료 동작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4d1e0f367ef167e5bf47d0936e0b3200ca7dbe19
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="instance-completion-action"></a>인스턴스 완료 동작
**인스턴스 완료 동작** SQL 워크플로 인스턴스 저장소의 속성을 사용 하면 삭제 여부를 데이터와 메타 데이터의 워크플로 인스턴스는 지 속성 데이터베이스에서 인스턴스를 완료 한 후를 지정할 수 있습니다. 이 속성에 대 한 허용 된 값은 **DeleteAll** 및 **DeleteNothing**합니다. 다음 목록에서는 이러한 옵션에 대해 설명합니다.  
  
-   **DeleteAll (기본값)입니다.** 속성의 값을 DeleteAll로 설정하면 인스턴스가 완료된 후 워크플로 인스턴스의 데이터와 메타데이터가 지속성 데이터베이스에서 삭제됩니다.  
  
-   **DeleteNothing 합니다.** 속성의 값을 DeleteNothing으로 설정하면 인스턴스가 완료된 후에도 워크플로 인스턴스의 데이터와 메타데이터가 지속성 데이터베이스에 그대로 유지됩니다.  
  
    > [!CAUTION]
    >  인스턴스가 완료된 후 인스턴스 상태 정보를 유지하면 지속성 데이터베이스의 크기가 증가합니다. 데이터베이스 크기가 증가할수록 지속성 하위 시스템이 수행하는 데이터베이스 작업이 더 오래 걸리므로, 서비스가 성능 필요에 맞는 수준으로 수행되도록 하려면 정기적으로 지속성 데이터베이스에서 인스턴스 상태 정보를 비워야 합니다.
