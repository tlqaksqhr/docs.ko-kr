---
title: 어셈블리 및 DLL의 이름
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6cf175472d68e99598dd56e170bee3d37ae3c2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570434"
---
# <a name="names-of-assemblies-and-dlls"></a>어셈블리 및 DLL의 이름
어셈블리는 배포 및 관리 코드 프로그램에 대 한 id의 단위입니다. 어셈블리 하나 이상의 파일에 걸쳐 있을 수 있습니다, 있지만 일반적으로 어셈블리가 매핑됩니다 DLL과 일 대 일로 합니다. 따라서이 섹션에서는 다음 어셈블리 명명 규칙으로 매핑할 수 있습니다만 DLL 명명 규칙을 설명 합니다.  
  
 **✓ 않습니다** 대량의 System.Data 등의 기능을 제안 하는 Dll 어셈블리의 이름을 선택 합니다.  
  
 DLL 이름은 네임 스페이스 이름에 해당 필요는 없지만 어셈블리의 이름을 지정할 때 네임 스페이스 이름 뒤에 적합 합니다. 경험에의 한 어셈블리에 포함 된 네임 스페이스의 공통 접두사에 따라 DLL 이름을 지정 하는 것입니다. 예를 들어 두 개의 네임 스페이스를 사용 하 여 어셈블리 `MyCompany.MyTechnology.FirstFeature` 및 `MyCompany.MyTechnology.SecondFeature`, 호출 될 수 있는 `MyCompany.MyTechnology.dll`합니다.  
  
 **✓ 고려** 다음 패턴에 따라 Dll 이름 지정:  
  
 `<Company>.<Component>.dll`  
  
 여기서 `<Component>` 점으로 구분 된 하나 이상의 절을 포함 합니다. 예를 들어:  
  
 `Litware.Controls.dll`.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
 [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)
