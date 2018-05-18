---
title: 판독기 및 작성기 잠금
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f829fc0b399f5cfd10d98f6b7439de757674f11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="reader-writer-locks"></a>판독기 및 작성기 잠금
<xref:System.Threading.ReaderWriterLockSlim> 클래스를 사용하면 여러 스레드가 리소스를 동시에 읽을 수 있지만 리소스에 쓰기 위해 스레드가 배타적 잠금을 기다려야 합니다.  
  
 응용 프로그램에서 <xref:System.Threading.ReaderWriterLockSlim>을 사용하여 공유 리소스에 액세스하는 스레드 간 협조적 동기화를 제공할 수 있습니다. 잠금은 <xref:System.Threading.ReaderWriterLockSlim> 자체에서 사용됩니다.  
  
 스레드 동기화 메커니즘과 마찬가지로 스레드가 <xref:System.Threading.ReaderWriterLockSlim>에 의해 제공되는 잠금을 바이패스하지 않는지 확인해야 합니다. 이를 확인하는 한 가지 방법은 공유 리소스를 캡슐화하는 클래스를 설계하는 것입니다. 이 클래스는 개인 공유 리소스에 액세스하고 동기화를 위해 개인 <xref:System.Threading.ReaderWriterLockSlim>을 사용하는 멤버를 제공합니다. 예를 들어 <xref:System.Threading.ReaderWriterLockSlim> 클래스에 대한 코드 예제를 참조하세요. <xref:System.Threading.ReaderWriterLockSlim>은 개별 개체를 동기화하는 데 사용될 만큼 충분히 효율적입니다.  
  
 읽기 및 쓰기 작업의 기간을 최소화하도록 응용 프로그램을 구성합니다. 쓰기 잠금이 배타적이기 때문에 긴 쓰기 작업은 처리량에 직접적으로 영향을 줍니다. 긴 읽기 작업은 작성기 대기를 차단하며 하나 이상의 스레드가 쓰기 액세스를 기다리고 있는 경우에는 읽기 액세스를 요청하는 스레드도 차단됩니다.  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에는 두 개의 판독기/작성기 잠금인 <xref:System.Threading.ReaderWriterLockSlim> 및 <xref:System.Threading.ReaderWriterLock>이 있습니다. <xref:System.Threading.ReaderWriterLockSlim>은 모든 새 개발에 권장됩니다. <xref:System.Threading.ReaderWriterLockSlim>은 <xref:System.Threading.ReaderWriterLock>과 비슷하지만 재귀 및 잠금 상태 업그레이드/다운그레이드에 대한 간소화된 규칙을 포함합니다. <xref:System.Threading.ReaderWriterLockSlim>은 교착 상태가 발생할 수 있는 많은 경우를 방지합니다. 또한 <xref:System.Threading.ReaderWriterLockSlim>의 성능이 <xref:System.Threading.ReaderWriterLock>보다 훨씬 더 놓습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.ReaderWriterLockSlim>  
 <xref:System.Threading.ReaderWriterLock>  
 [스레딩](../../../docs/standard/threading/index.md)  
 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md)
