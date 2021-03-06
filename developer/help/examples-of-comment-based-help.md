---
title: 주석 기반 도움말의 예 | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 868194a2-17e9-4184-bc36-c04a33f26494
caps.latest.revision: 4
ms.openlocfilehash: dbccaf5b8e48a1c4d924bc0ec4ea09b25e10adf0
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857969"
---
# <a name="examples-of-comment-based-help"></a>설명 기반 도움말 예제

이 항목에서는 스크립트 및 함수에 대 한 설명 기반 도움말을 사용 하는 방법을 보여 주는 예제를 포함 합니다.

## <a name="example-1-comment-based-help-for-a-function"></a>예제 1: 함수에 대 한 설명 기반 도움말

 다음 샘플 함수 설명 기반 도움말을 포함합니다.

```powershell
function Add-Extension
{
    param ([string]$Name,[string]$Extension = "txt")
    $name = $name + "." + $extension
    $name

    <#
        .SYNOPSIS
        Adds a file name extension to a supplied name.

        .DESCRIPTION
        Adds a file name extension to a supplied name.
        Takes any strings for the file name or extension.

        .PARAMETER Name
        Specifies the file name.

        .PARAMETER Extension
        Specifies the extension. "Txt" is the default.

        .INPUTS
        None. You cannot pipe objects to Add-Extension.

        .OUTPUTS
        System.String. Add-Extension returns a string with the extension or file name.

        .EXAMPLE
        C:\PS> extension -name "File"
        File.txt

        .EXAMPLE
        C:\PS> extension -name "File" -extension "doc"
        File.doc

        .EXAMPLE
        C:\PS> extension "File" "doc"
        File.doc

        .LINK
        Online version: http://www.fabrikam.com/extension.html

        .LINK
        Set-Item
    #>
}
```

다음과 같은 출력이 추가 확장 함수에 대 한 도움말을 표시 하는 Get-help 명령의 결과 보여 줍니다.

```powershell
C:\PS> get-help add-extension -full
```

```output
        NAME
            Add-Extension

        SYNOPSIS
            Adds a file name extension to a supplied name.

        SYNTAX
            Add-Extension [[-Name] <String>] [[-Extension] <String>] [<CommonParameters>]

        DESCRIPTION
            Adds a file name extension to a supplied name. Takes any strings for the file name or extension.

        PARAMETERS
           -Name
               Specifies the file name.

               Required?                    false
               Position?                    0
               Default value
               Accept pipeline input?       false
               Accept wildcard characters?

           -Extension
               Specifies the extension. "Txt" is the default.

               Required?                    false
               Position?                    1
               Default value
               Accept pipeline input?       false
               Accept wildcard characters?

            <CommonParameters>
               This cmdlet supports the common parameters: -Verbose, -Debug,
               -ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
               -OutBuffer and -OutVariable. For more information, type
               "get-help about_commonparameters".

        INPUTS
            None. You cannot pipe objects to Add-Extension.

        OUTPUTS
            System.String. Add-Extension returns a string with the extension or file name.

            -------------------------- EXAMPLE 1 --------------------------

            C:\PS> extension -name "File"
            File.txt

            -------------------------- EXAMPLE 2 --------------------------

            C:\PS> extension -name "File" -extension "doc"
            File.doc

            -------------------------- EXAMPLE 3 --------------------------

            C:\PS> extension "File" "doc"
            File.doc

        RELATED LINKS
            Online version: http://www.fabrikam.com/extension.html
            Set-Item
```

## <a name="example-2-comment-based-help-for-a-script"></a>예제 2: 스크립트에 대 한 설명 기반 도움말

다음 샘플 함수 설명 기반 도움말을 포함합니다.

닫는 사이의 빈 줄을 확인할 수 있습니다 **#>** 고 `Param` 문입니다. 없는 스크립트에는 `Param` 문을 도움말 항목의 최종 주석 사이 첫 번째 함수 선언 두 개 이상의 빈 줄 여야 합니다. 이러한 빈 줄 없이 Get-help 스크립트 대신 함수를 사용 하 여 도움말 항목을 연결합니다.

```powershell
<#
  .SYNOPSIS
  Performs monthly data updates.

  .DESCRIPTION
  The Update-Month.ps1 script updates the registry with new data generated
  during the past month and generates a report.

  .PARAMETER InputPath
  Specifies the path to the CSV-based input file.

  .PARAMETER OutputPath
  Specifies the name and path for the CSV-based output file. By default,
  MonthlyUpdates.ps1 generates a name from the date and time it runs, and
  saves the output in the local directory.

  .INPUTS
  None. You cannot pipe objects to Update-Month.ps1.

  .OUTPUTS
  None. Update-Month.ps1 does not generate any output.

  .EXAMPLE
  C:\PS> .\Update-Month.ps1

  .EXAMPLE
  C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

  .EXAMPLE
  C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath C:\Reports\2009\January.csv
#>

param ([string]$InputPath, [string]$OutPutPath)

function Get-Data { }
```

다음 명령은 스크립트를 도움말을 가져옵니다. 스크립트를 n 없기 때문에 도움말 스크립트를 가져오는 Get-help 명령은 Path 환경 변수에 나열 된 디렉터리의 스크립트 경로 지정 해야 합니다.

```powershell
C:\PS> get-help c:\ps-test\update-month.ps1 -full
```

```output
            NAME
                C:\ps-test\Update-Month.ps1

            SYNOPSIS
                Performs monthly data updates.

            SYNTAX
                C:\ps-test\Update-Month.ps1 [-InputPath] <String> [[-OutputPath]
                <String>] [<CommonParameters>]

            DESCRIPTION
                The Update-Month.ps1 script updates the registry with new data
                generated during the past month and generates a report.

            PARAMETERS
               -InputPath
                   Specifies the path to the CSV-based input file.

                   Required?                    true
                   Position?                    0
                   Default value
                   Accept pipeline input?       false
                   Accept wildcard characters?

               -OutputPath
                   Specifies the name and path for the CSV-based output file. By
                   default, MonthlyUpdates.ps1 generates a name from the date
                   and time it runs, and saves the output in the local directory.

                   Required?                    false
                   Position?                    1
                   Default value
                   Accept pipeline input?       false
                   Accept wildcard characters?

               <CommonParameters>
                   This cmdlet supports the common parameters: -Verbose, -Debug,
                   -ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
                   -OutBuffer and -OutVariable. For more information, type,
                   "get-help about_commonparameters".

            INPUTS
                   None. You cannot pipe objects to Update-Month.ps1.

            OUTPUTS
                   None. Update-Month.ps1 does not generate any output.

            -------------------------- EXAMPLE 1 --------------------------

            C:\PS> .\Update-Month.ps1

            -------------------------- EXAMPLE 2 --------------------------

            C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

            -------------------------- EXAMPLE 3 --------------------------

            C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath
            C:\Reports\2009\January.csv

            RELATED LINKS
```

## <a name="example-3-parameter-descriptions-in-a-param-statement"></a>예제 3: Param 문에서 매개 변수 설명

이 예제에서 parameterdescriptions 삽입 하는 방법을 표시 합니다 `Param` 함수 또는 스크립트의 문을 합니다. 이 형식 매개 변수 설명을 간단 하 게 하는 경우 가장 유용 합니다.

```powershell
function Add-Extension
{
    param
    (
        [string]
        # Specifies the file name.
        $name,

        [string]
        # Specifies the file name extension. "Txt" is the default.
        $extension = "txt"
    )
    $name = $name + "." + $extension
    $name

    <#
        .SYNOPSIS
        Adds a file name extension to a supplied name.
...
    #>
```

결과 결과 예를 들어 1로 동일 합니다. Get-help 수반 된 것 처럼 매개 변수 설명을 해석 된 `.Parameter` 키워드입니다.

## <a name="example-4--redirecting-to-an-xml-file"></a>예제 4:  XML 파일에 리디렉션

함수 및 스크립트에 대 한 XML 기반 도움말 항목을 작성할 수 있습니다. 주석 기반 도움말을 보다 쉽게 구현할 수 있지만 XML 기반 도움말은 도움말 콘텐츠 또는 도움말 항목을 여러 언어로 번역 하는 경우 보다 정밀 하 게 제어 하려는 경우에 필요. 다음 예제에서는 업데이트 Month.ps1 스크립트의 처음 몇 줄을 보여 줍니다. 스크립트를 사용 하는 `.ExternalHelp` 키워드를 스크립트에 대 한 XML 기반 도움말 항목의 경로 지정 합니다.

```powershell
#  .ExternalHelp C:\MyScripts\Update-Month-Help.xml

    param ([string]$InputPath, [string]$OutPutPath)

    function Get-Data { }
```

다음 예제에서는 사용 된 `.ExternalHelp` 함수에서 키워드.

```powershell
function Add-Extension
{
    param ([string] $name, [string]$extension = "txt")
    $name = $name + "." + $extension
    $name

    # .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

## <a name="example-5--redirecting-to-a-different-help-topic"></a>예제 5:  다른 도움말 항목으로 리디렉션

다음 코드는 기본 제공의 시작 부분에서 발췌 한 `Help` Windows powershell에서 한 번에 하나의 텍스트 화면을 도움말을 표시 하는 함수입니다. Help 함수에 사용 하 여 도움말 기능을 설명 하는 Get-help cmdlet에 대 한 도움말 항목, 때문에 합니다 `.ForwardHelpTargetName` 및 `.ForwardHelpCategory` 키워드 Get-help cmdlet 도움말 항목에는 사용자를 리디렉션합니다.

```powershell
function help
{

    <#
      .FORWARDHELPTARGETNAME Get-Help
      .FORWARDHELPCATEGORY Cmdlet
    #>
    [CmdletBinding(DefaultParameterSetName='AllUsersView')]
    param(
            [Parameter(Position=0, ValueFromPipelineByPropertyName=$true)]
            [System.String]
            ${Name},
    ...
```

다음 명령은이 기능을 사용 합니다. Help 함수에 대 한 Get-help 명령을 입력 한 사용자, Get-help Get-help cmdlet에 대 한 도움말 항목을 표시 합니다.

```powershell
C:\PS> get-help help
```

```output
            NAME
                Get-Help

            SYNOPSIS
                Displays information about Windows PowerShell cmdlets and concepts.
            ...
```