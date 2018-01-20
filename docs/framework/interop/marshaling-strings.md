---
title: "문자열 마샬링"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- marshaling, samples
- platform invoke, marshaling data
- data marshaling, strings
- data marshaling, samples
- data marshaling, platform invoke
- marshaling. strings
- marshaling, platform invoke
- sample applications [.NET Framework], marshaling strings
ms.assetid: e21b078b-70fb-4905-be26-c097ab2433ff
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a4d53cd4072ab3f9ff52729f122c0a0ecab400df
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="marshaling-strings"></a>문자열 마샬링
플랫폼 호출은 문자열 매개 변수를 복사하고 필요한 경우 .NET Framework 형식(유니코드)을 관리되지 않는 형식(ANSI)으로 변환합니다. 관리되는 문자열은 변경할 수 없으므로 함수가 반환할 때 플랫폼 호출을 통해 해당 문자열을 관리되지 않는 메모리에서 관리되는 메모리로 다시 복사하지 않습니다.  
  
 다음 표에서는 문자열에 대한 마샬링 옵션을 나열하고 용도를 설명하며 해당하는 .NET Framework 샘플에 대한 링크를 제공합니다.  
  
|문자열|설명|샘플|  
|------------|-----------------|------------|  
|값.|문자열을 In 매개 변수로 전달합니다.|[MsgBox](../../../docs/framework/interop/msgbox-sample.md)|  
|결과.|비관리 코드에서 문자열을 반환합니다.|[문자열](http://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|참조.|<xref:System.Text.StringBuilder>를 사용하여 In/Out 매개 변수로 문자열을 전달합니다.|[버퍼](http://msdn.microsoft.com/library/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5)|  
|값 방식 구조체.|In 매개 변수에 있는 구조체에 문자열을 전달합니다.|[구조체](http://msdn.microsoft.com/library/96a62265-dcf9-4608-bc0a-1f762ab9f48e)|  
|참조 방식 구조체**(char\*)**.|In/Out 매개 변수에 있는 구조체에 문자열을 전달합니다. 관리되지 않는 함수에는 문자 버퍼에 대한 포인터가 필요하며 버퍼 크기는 구조체의 멤버입니다.|[문자열](http://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|참조 방식 구조체**(char[])**.|In/Out 매개 변수에 있는 구조체에 문자열을 전달합니다. 관리되지 않는 함수에는 포함된 문자 버퍼가 있어야 합니다.|[OSInfo](http://msdn.microsoft.com/library/69d89067-507b-41fe-859d-30bf3ff29455)|  
|값 방식 클래스**(char\*)**.|클래스에 문자열을 전달합니다(클래스는 In/Out 매개 변수임). 관리되지 않는 함수에는 문자 버퍼에 대한 포인터가 있어야 합니다.|[OpenFileDlg](http://msdn.microsoft.com/library/b7dea792-cb92-4baf-ac7b-6a24803e6c75)|  
|값 방식 클래스**(char[])**.|클래스에 문자열을 전달합니다(클래스는 In/Out 매개 변수임). 관리되지 않는 함수에는 포함된 문자 버퍼가 있어야 합니다.|[OSInfo](http://msdn.microsoft.com/library/69d89067-507b-41fe-859d-30bf3ff29455)|  
|값 형식 문자열 배열.|값으로 전달되는 문자열의 배열을 만듭니다.|[배열](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
|값 형식 문자열을 포함하는 구조체의 배열.|문자열을 포함하는 구조체의 배열을 만들고 배열을 값으로 전달합니다.|[배열](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a>참고 항목  
 [플랫폼 호출을 사용하여 데이터 마샬링](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)  
 [플랫폼 호출 데이터 형식](http://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f)  
 [클래스, 구조체 및 공용 구조체 마샬링](../../../docs/framework/interop/marshaling-classes-structures-and-unions.md)  
 [형식 배열 마샬링](http://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8)  
 [기타 마샬링 샘플](http://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70)
