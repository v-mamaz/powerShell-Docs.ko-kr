---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: ISE 개체 모델 계층 구조
ms.openlocfilehash: 0159707b1050c412a74da3d3ca02a46cea982556
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403132"
---
# <a name="the-ise-object-model-hierarchy"></a>ISE 개체 모델 계층 구조

이 항목에서는 Windows PowerShell ISE(통합 스크립팅 환경)에 속하는 개체의 계층 구조를 보여 줍니다.
Windows PowerShell ISE는 Windows PowerShell 3.0 및 Windows PowerShell 4.0에 포함되어 있습니다.
개체를 클릭하여 개체를 정의하는 클래스에 대한 참조 설명서로 이동합니다.

## <a name="psise-object"></a>$psISE 개체

**$psISE** 개체는 Windows PowerShell ISE 개체 계층 구조의 [루트 개체](The-ObjectModelRoot-Object.md)입니다.
최상위 수준에 있는 이 개체를 사용하면 스크립팅에 다음 개체를 사용할 수 있습니다.

## <a name="psisecurrentfilethe-isefile-objectmd"></a>[$psISE.CurrentFile](The-ISEFile-Object.md)

**$psISE.CurrentFile** 개체는 [ISEFile](The-ISEFile-Object.md) 클래스의 인스턴스입니다.

## <a name="psisecurrentpowershelltabthe-powershelltab-objectmd"></a>[$psISE.CurrentPowerShellTab](The-PowerShellTab-Object.md)

**$psISE.CurrentPowerShellTab** 개체는 [PowerShellTab](The-PowerShellTab-Object.md) 클래스의 인스턴스입니다.

## <a name="psisecurrentvisiblehorizontaltool"></a>$psISE.CurrentVisibleHorizontalTool

**$psISE.CurrentVisibleHorizontalTool** 개체는 [ISEAddOnTool](The-ISEAddOnTool-Object.md) 클래스의 인스턴스입니다.
현재 Windows PowerShell ISE 창의 위쪽 가장자리에 도킹되어 있는 설치된 추가 기능 도구를 나타냅니다.

## <a name="psisecurrentvisibleverticaltool"></a>$psISE.CurrentVisibleVerticalTool

**$psISE.CurrentVisibleHorizontalTool** 개체는 [ISEAddOnTool](The-ISEAddOnTool-Object.md) 클래스의 인스턴스입니다.
현재 Windows PowerShell ISE 창의 오른쪽 가장자리에 도킹되어 있는 설치된 추가 기능 도구를 나타냅니다.

## <a name="psiseoptionsthe-iseoptions-objectmd"></a>[$psISE.Options](The-ISEOptions-Object.md)

**$psISE.Options** 개체는 [ISEOptions](The-ISEOptions-Object.md) 클래스의 인스턴스입니다.
ISEOptions 개체는 Windows PowerShell ISE에 대한 다양한 설정을 나타냅니다.
Microsoft.PowerShell.Host.ISE.ISEOptions 클래스의 인스턴스입니다.

## <a name="psisepowershelltabsthe-powershelltabcollection-objectmd"></a>[$psISE.PowerShellTabs](The-PowerShellTabCollection-Object.md)

**$psISE.PowerShellTabs** 개체는 [PowerShellTabCollection](The-PowerShellTabCollection-Object.md) 클래스의 인스턴스입니다.
로컬 컴퓨터 또는 연결된 원격 컴퓨터에서 사용 가능한 Windows PowerShell 실행 환경을 나타내는 현재 열려 있는 모든 PowerShell 탭의 모음입니다.
컬렉션의 각 멤버는 [PowerShellTab](The-PowerShellTab-Object.md) 클래스의 인스턴스입니다.

## <a name="see-also"></a>참고 항목

- [Windows PowerShell ISE 스크립팅 개체 모델의 용도](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [ISE 개체 모델 계층 구조](The-ISE-Object-Model-Hierarchy.md)