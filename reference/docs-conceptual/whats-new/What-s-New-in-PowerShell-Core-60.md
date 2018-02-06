# <a name="whats-new-in-powershell-core-60"></a><span data-ttu-id="805fb-101">PowerShell Core 6.0의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="805fb-101">What's New in PowerShell Core 6.0</span></span>

<span data-ttu-id="805fb-102">[PowerShell Core 6.0][github]은 PowerShell의 새로운 버전으로, 크로스 플랫폼(Windows, macOS 및 Linux)이자 오픈 소스이며 다른 유형의 환경 및 하이브리드 클라우드용으로 빌드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-102">[PowerShell Core 6.0][github] is a new edition of PowerShell that is cross-platform (Windows, macOS, and Linux), open-source, and built for heterogeneous environments and the hybrid cloud.</span></span>

## <a name="moved-from-net-framework-to-net-core"></a><span data-ttu-id="805fb-103">.NET Framework에서 .NET Core로 이동됨</span><span class="sxs-lookup"><span data-stu-id="805fb-103">Moved from .NET Framework to .NET Core</span></span>

<span data-ttu-id="805fb-104">PowerShell Core는 [.NET Core 2.0][]을 런타임으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-104">PowerShell Core uses [.NET Core 2.0][] as its runtime.</span></span>
<span data-ttu-id="805fb-105">.NET Core 2.0을 사용하면 PowerShell Core가 여러 플랫폼(Windows, macOS 및 Linux)에서 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-105">.NET Core 2.0 enables PowerShell Core to work on multiple platforms (Windows, macOS, and Linux).</span></span>
<span data-ttu-id="805fb-106">또한 PowerShell Core는 PowerShell cmdlet 및 스크립트에서 사용하도록 .NET Core 2.0에서 제공하는 API 집합을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-106">PowerShell Core also exposes the API set offered by .NET Core 2.0 to be used in PowerShell cmdlets and scripts.</span></span>

<span data-ttu-id="805fb-107">Windows PowerShell은 .NET Framework 런타임을 사용하여 PowerShell 엔진을 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-107">Windows PowerShell used the .NET Framework runtime to host the PowerShell engine.</span></span>
<span data-ttu-id="805fb-108">즉, Windows PowerShell은 .NET Framework에서 제공하는 API 집합을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-108">This means that Windows PowerShell exposes the API set offered by .NET Framework.</span></span>

<span data-ttu-id="805fb-109">.NET Core와 .NET Framework 간에서 공유된 API는 [.NET Standard][]의 일부로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-109">The APIs shared between .NET Core and .NET Framework are defined as part of [.NET Standard][].</span></span>

<span data-ttu-id="805fb-110">이것이 PowerShell Core와 Windows PowerShell 간의 모듈/스크립트 호환성에 미치는 영향에 대한 자세한 내용은 [Windows PowerShell 이전 버전과의 호환성][# backwards-compatibility-with-windows-powershell](#backwards-compatibility-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="805fb-110">For more information on how this affects module/script compatibility between PowerShell Core and Windows PowerShell, see [Backwards compatibility with Windows PowerShell](#backwards-compatibility-with-windows-powershell).</span></span>

## <a name="support-for-macos-and-linux"></a><span data-ttu-id="805fb-111">macOS 및 Linux 지원</span><span class="sxs-lookup"><span data-stu-id="805fb-111">Support for macOS and Linux</span></span>

<span data-ttu-id="805fb-112">PowerShell은 이제 다음을 포함하여 공식적으로 macOS 및 Linux를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-112">PowerShell now officially supports macOS and Linux, including:</span></span>

- <span data-ttu-id="805fb-113">Windows 7, 8.1, 10</span><span class="sxs-lookup"><span data-stu-id="805fb-113">Windows 7, 8.1, and 10</span></span>
- <span data-ttu-id="805fb-114">Windows Server 2008 R2, 2012 R2, 2016</span><span class="sxs-lookup"><span data-stu-id="805fb-114">Windows Server 2008 R2, 2012 R2, 2016</span></span>
- <span data-ttu-id="805fb-115">[Windows 서버 반기 채널][semi-annual]</span><span class="sxs-lookup"><span data-stu-id="805fb-115">[Windows Server Semi-Annual Channel][semi-annual]</span></span>
- <span data-ttu-id="805fb-116">Ubuntu 14.04, 16.04, 17.04</span><span class="sxs-lookup"><span data-stu-id="805fb-116">Ubuntu 14.04, 16.04, and 17.04</span></span>
- <span data-ttu-id="805fb-117">Debian 8.7+, 9</span><span class="sxs-lookup"><span data-stu-id="805fb-117">Debian 8.7+, and 9</span></span>
- <span data-ttu-id="805fb-118">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="805fb-118">CentOS 7</span></span>
- <span data-ttu-id="805fb-119">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="805fb-119">Red Hat Enterprise Linux 7</span></span>
- <span data-ttu-id="805fb-120">OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="805fb-120">OpenSUSE 42.2</span></span>
- <span data-ttu-id="805fb-121">Fedora 25, 26</span><span class="sxs-lookup"><span data-stu-id="805fb-121">Fedora 25, 26</span></span>
- <span data-ttu-id="805fb-122">macOS 10.12+</span><span class="sxs-lookup"><span data-stu-id="805fb-122">macOS 10.12+</span></span>

<span data-ttu-id="805fb-123">또한 커뮤니티에서 다음 플랫폼과 관련한 패키지를 제공하였으나 공식적으로 지원되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-123">Our community has also contributed packages for the following platforms, but they are not officially supported:</span></span>

- <span data-ttu-id="805fb-124">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="805fb-124">Arch Linux</span></span>
- <span data-ttu-id="805fb-125">Kali Linux</span><span class="sxs-lookup"><span data-stu-id="805fb-125">Kali Linux</span></span>
- <span data-ttu-id="805fb-126">AppImage(여러 Linux 플랫폼에서 사용)</span><span class="sxs-lookup"><span data-stu-id="805fb-126">AppImage (works on multiple Linux platforms)</span></span>

<span data-ttu-id="805fb-127">또한 다음 플랫폼에 대해 실험적(지원되지 않는) 릴리스도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-127">We also have experimental (unsupported) releases for the following platforms:</span></span>

- <span data-ttu-id="805fb-128">Windows on ARM32/ARM64</span><span class="sxs-lookup"><span data-stu-id="805fb-128">Windows on ARM32/ARM64</span></span>
- <span data-ttu-id="805fb-129">Raspbian(Stretch)</span><span class="sxs-lookup"><span data-stu-id="805fb-129">Raspbian (Stretch)</span></span>

<span data-ttu-id="805fb-130">비 Windows 시스템에서 잘 작동하도록 PowerShell Core 6.0에서 여러 가지가 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-130">A number of changes were made to in PowerShell Core 6.0 to make it work better on non-Windows systems.</span></span>
<span data-ttu-id="805fb-131">이들 중 일부는 Windows에 영향을 주는 주요 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-131">Some of these are breaking changes, which also affect Windows.</span></span>
<span data-ttu-id="805fb-132">다른 변경 사항은 비 Windows에 PowerShell Core가 설치된 경우에만 제공되거나 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-132">Others are only present or applicable in non-Windows installations of PowerShell Core.</span></span>

- <span data-ttu-id="805fb-133">Unix 플랫폼에서 기본 명령 와일드 카드 사용 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-133">Added support for native command globbing on Unix platforms.</span></span>
- <span data-ttu-id="805fb-134">`more` 기능은 Linux `$PAGER`를 따르며 기본값은 `less`입니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-134">The `more` functionality respects the Linux `$PAGER` and defaults to `less`.</span></span>
  <span data-ttu-id="805fb-135">즉, 네이티브 바이너리/명령(예: `ls *.txt`)과 함께 와일드 카드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-135">This means you can now use wildcards with native binaries/commands (for example, `ls *.txt`).</span></span> <span data-ttu-id="805fb-136">(#3463)</span><span class="sxs-lookup"><span data-stu-id="805fb-136">(#3463)</span></span>
- <span data-ttu-id="805fb-137">네이티브 명령 인수를 처리할 때 후행 백슬래시가 자동으로 이스케이프됩니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-137">Trailing backslash is automatically escaped when dealing with native command arguments.</span></span> <span data-ttu-id="805fb-138">(#4965)</span><span class="sxs-lookup"><span data-stu-id="805fb-138">(#4965)</span></span>
- <span data-ttu-id="805fb-139">현재 스크립트 서명이 지원되지 않기 때문에 Windows 이외의 플랫폼에서 PowerShell을 실행할 때 `-ExecutionPolicy` 스위치를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-139">Ignore the `-ExecutionPolicy` switch when running PowerShell on non-Windows platforms because script signing is not currently supported.</span></span> <span data-ttu-id="805fb-140">(#3481)</span><span class="sxs-lookup"><span data-stu-id="805fb-140">(#3481)</span></span>
- <span data-ttu-id="805fb-141">Unix 플랫폼에서 `NoEcho`를 지원하기 위해 ConsoleHost가 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-141">Fixed ConsoleHost to honor `NoEcho` on Unix platforms.</span></span> <span data-ttu-id="805fb-142">(#3801)</span><span class="sxs-lookup"><span data-stu-id="805fb-142">(#3801)</span></span>
- <span data-ttu-id="805fb-143">Unix 플랫폼에서 대/소문자를 구분하지 않는 패턴 일치를 지원하도록 `Get-Help`가 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-143">Fixed `Get-Help` to support case insensitive pattern matching on Unix platforms.</span></span> <span data-ttu-id="805fb-144">(#3852)</span><span class="sxs-lookup"><span data-stu-id="805fb-144">(#3852)</span></span>
- <span data-ttu-id="805fb-145">패키지에 `powershell` man-page 추가됨</span><span class="sxs-lookup"><span data-stu-id="805fb-145">`powershell` man-page added to package</span></span>

### <a name="logging"></a><span data-ttu-id="805fb-146">로깅</span><span class="sxs-lookup"><span data-stu-id="805fb-146">Logging</span></span>

<span data-ttu-id="805fb-147">macOS에서 PowerShell은 기본 `os_log` API를 사용하여 Apple의 [통합 로깅 시스템][os_log]에 로깅합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-147">On macOS, PowerShell uses the native `os_log` APIs to log to Apple's [unified logging system][os_log].</span></span>
<span data-ttu-id="805fb-148">Linux에서 PowerShell은 유비쿼터스 로깅 솔루션인 [Syslog][]를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-148">On Linux, PowerShell uses [Syslog][], a ubiquitous logging solution.</span></span>

### <a name="filesystem"></a><span data-ttu-id="805fb-149">파일 시스템</span><span class="sxs-lookup"><span data-stu-id="805fb-149">Filesystem</span></span>

<span data-ttu-id="805fb-150">Windows에서 일반적으로 지원되지 않는 파일 이름 문자를 지원하도록 macOS 및 Linux에서 많은 변경이 이루어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-150">A number of changes have been made on macOS and Linux to support filename characters not traditionally supported on Windows:</span></span>

- <span data-ttu-id="805fb-151">cmdlet에 지정된 경로는 이제 슬래시를 구분하지 않습니다(/ 및 \ 모두 디렉터리 구분 기호로 사용).</span><span class="sxs-lookup"><span data-stu-id="805fb-151">Paths given to cmdlets are now slash-agnostic (both / and \ work as directory separator)</span></span>
- <span data-ttu-id="805fb-152">기본적으로 이제 XDG 기본 디렉터리 지정이 적용되고 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-152">XDG Base Directory Specification is now respected and used by default:</span></span>
  - <span data-ttu-id="805fb-153">Linux/macOS 프로필 경로는 `~/.config/powershell/profile.ps1`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-153">The Linux/macOS profile path is located at `~/.config/powershell/profile.ps1`</span></span>
  - <span data-ttu-id="805fb-154">기록 저장 경로는 `~/.local/share/powershell/PSReadline/ConsoleHost_history.txt`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-154">The history save path is located at `~/.local/share/powershell/PSReadline/ConsoleHost_history.txt`</span></span>
  - <span data-ttu-id="805fb-155">사용자 모듈 경로는 `~/.local/share/powershell/Modules`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-155">The user module path is located at `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="805fb-156">Unix에서 콜론 문자가 포함된 파일 및 폴더 이름을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-156">Support for file and folder names containing the colon character on Unix.</span></span> <span data-ttu-id="805fb-157">(#4959)</span><span class="sxs-lookup"><span data-stu-id="805fb-157">(#4959)</span></span>
- <span data-ttu-id="805fb-158">스크립트 이름이나 콤마가 포함된 전체 경로를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-158">Support for script names or full paths that have commas.</span></span> <span data-ttu-id="805fb-159">(#4136) (@TimCurwick에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-159">(#4136) (Thanks to @TimCurwick!)</span></span>
- <span data-ttu-id="805fb-160">탐색 cmdlet의 와일드 카드를 확장하지 않기 위해 `-LiteralPath`를 사용할 때 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-160">Detect when `-LiteralPath` is used to suppress wildcard expansion for navigation cmdlets.</span></span> <span data-ttu-id="805fb-161">(#5038)</span><span class="sxs-lookup"><span data-stu-id="805fb-161">(#5038)</span></span>
- <span data-ttu-id="805fb-162">\*nix `ls -R` 및 Windows `DIR /S` 네이티브 명령 등을 실행하도록 `Get-ChildItem`이 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-162">Updated `Get-ChildItem` to work more like the \*nix `ls -R` and the Windows `DIR /S` native commands.</span></span>
  <span data-ttu-id="805fb-163">`Get-ChildItem`은 재귀 검색 중에 발견된 심볼릭 링크를 반환하고 대상과 연결되는 디렉터리를 검색하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-163">`Get-ChildItem` now returns the symbolic links encountered during a recursive search and does not search the directories that those links target.</span></span> <span data-ttu-id="805fb-164">(#3780)</span><span class="sxs-lookup"><span data-stu-id="805fb-164">(#3780)</span></span>

### <a name="case-sensitivity"></a><span data-ttu-id="805fb-165">대/소문자 구분</span><span class="sxs-lookup"><span data-stu-id="805fb-165">Case sensitivity</span></span>

<span data-ttu-id="805fb-166">Linux와 macOS는 대/소문자를 구분하지만 Windows는 대/소문자를 유지하면서 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-166">Linux and macOS tend to be case-sensitive while Windows is case-insensitive while preserving case.</span></span>
<span data-ttu-id="805fb-167">일반적으로 PowerShell은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-167">In general, PowerShell is case insensitive.</span></span>

<span data-ttu-id="805fb-168">예를 들어, 환경 변수는 macOS 및 Linux에서 대/소문자를 구분하므로 `PSModulePath` 환경 변수의 대/소문자가 표준화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-168">For example, environment variables are case-sensitive on macOS and Linux, so the casing of the `PSModulePath` environment variable has been standardized.</span></span> <span data-ttu-id="805fb-169">(# 3255) `Import-Module`은 파일 경로를 사용하여 모듈의 이름을 구분할 때 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-169">(#3255) `Import-Module` is case insensitive when it's using a file path to determine the module's name.</span></span> <span data-ttu-id="805fb-170">(#5097)</span><span class="sxs-lookup"><span data-stu-id="805fb-170">(#5097)</span></span>

## <a name="support-for-side-by-side-installations"></a><span data-ttu-id="805fb-171">병렬 설치 지원</span><span class="sxs-lookup"><span data-stu-id="805fb-171">Support for side-by-side installations</span></span>

<span data-ttu-id="805fb-172">PowerShell Core는 Windows PowerShell과 별도로 설치, 구성 및 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-172">PowerShell Core is installed, configured, and executed separately from Windows PowerShell.</span></span>
<span data-ttu-id="805fb-173">PowerShell Core에는 "휴대용" ZIP 패키지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-173">PowerShell Core has a "portable" ZIP package.</span></span>
<span data-ttu-id="805fb-174">ZIP 패키지를 사용하면 PowerShell을 종속 요소로 사용하는 응용 프로그램에 로컬로 설치하는 등 디스크의 어느 위치에나 원하는 버전을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-174">Using the ZIP package, you can install any number of versions anywhere on disk, including local to an application that takes PowerShell as a dependency.</span></span>
<span data-ttu-id="805fb-175">병렬 설치를 통해 새로운 버전의 PowerShell을 쉽게 테스트하고 기존 스크립트를 시간에 따라 마이그레이션할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="805fb-175">Side-by-side installation makes it easier to test new versions of PowerShell and migrating existing scripts over time.</span></span>
<span data-ttu-id="805fb-176">병렬 설치는 또한 스크립트가 필요로 하는 특정 버전에 고정될 수 있으므로 이전 버전과의 호환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-176">Side-by-side also enables backwards compatibility as scripts can be pinned to specific versions that they require.</span></span>

> [!NOTE]
> <span data-ttu-id="805fb-177">기본적으로 Windows의 MSI 기반 설치 관리자는 적절한 업데이트 설치를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-177">By default, the MSI-based installer on Windows does an in-place update install.</span></span>
>

## <a name="renamed-powershellexe-to-pwshexe"></a><span data-ttu-id="805fb-178">`powershell(.exe)`에서 `pwsh(.exe)`로 이름이 변경됨</span><span class="sxs-lookup"><span data-stu-id="805fb-178">Renamed `powershell(.exe)` to `pwsh(.exe)`</span></span>

<span data-ttu-id="805fb-179">PowerShell Core의 이진 이름이 `powershell(.exe)`에서 `pwsh(.exe)`로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-179">The binary name for PowerShell Core has been changed from `powershell(.exe)` to `pwsh(.exe)`.</span></span>
<span data-ttu-id="805fb-180">이 변경은 사용자가 Windows PowerShell 및 PowerShell Core의 병렬 설치를 지원하는 컴퓨터에서 사용자가 PowerShell Core를 실행할 수 있는 결정적인 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-180">This change provides a deterministic way for users to run PowerShell Core on machines to support side-by-side Windows PowerShell and PowerShell Core installations.</span></span>
<span data-ttu-id="805fb-181">`pwsh`는 또한 훨씬 짧고 쉽게 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-181">`pwsh` is also much shorter and easier to type.</span></span>

<span data-ttu-id="805fb-182">`powershell.exe`에서 `pwsh(.exe)`로의 추가 변경 사항:</span><span class="sxs-lookup"><span data-stu-id="805fb-182">Additional changes to `pwsh(.exe)` from `powershell.exe`:</span></span>

- <span data-ttu-id="805fb-183">첫 번째 위치 매개 변수를 `-Command`에서 `-File`로 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-183">Changed the first positional parameter from `-Command` to `-File`.</span></span>
  <span data-ttu-id="805fb-184">이 변경 사항은 Windows 이외의 플랫폼에서 PowerShell이 아닌 셸에서 실행되는 PowerShell 스크립트에서 `#!`의 사용(즉, shebang)을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-184">This change fixes the usage of `#!` (aka as a shebang) in PowerShell scripts that are being executed from non-PowerShell shells on non-Windows platforms.</span></span>
  <span data-ttu-id="805fb-185">또한 `-File`을 지정하지 않고 `pwsh foo.ps1` 또는 `pwsh fooScript`와 같은 명령을 실행할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-185">It also means that you can run commands like `pwsh foo.ps1` or `pwsh fooScript` without specifying `-File`.</span></span>
  <span data-ttu-id="805fb-186">그러나 이 변경 사항은 `pwsh.exe -Command Get-Command`와 같은 명령을 실행하려고 할 때 `-c` 또는 `-Command`을 명시적으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-186">However, this change requires that you explicitly specify `-c` or `-Command` when trying to run commands like `pwsh.exe -Command Get-Command`.</span></span> <span data-ttu-id="805fb-187">(#4019)</span><span class="sxs-lookup"><span data-stu-id="805fb-187">(#4019)</span></span>
- <span data-ttu-id="805fb-188">PowerShell Core는 대화형 셸을 나타내기 위해 `-i`(또는 `-Interactive`) 스위치를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-188">PowerShell Core accepts the `-i` (or `-Interactive`) switch to indicate an interactive shell.</span></span> <span data-ttu-id="805fb-189">(# 3558) 이렇게 하면 Unix 플랫폼에서 PowerShell을 기본 셸로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-189">(#3558) This allows PowerShell to be used as a default shell on Unix platforms.</span></span>
- <span data-ttu-id="805fb-190">`pwsh.exe`에서 매개 변수 `-importsystemmodules` 및 `-psconsoleFile`을 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-190">Removed parameters `-importsystemmodules` and `-psconsoleFile` from `pwsh.exe`.</span></span> <span data-ttu-id="805fb-191">(#4995)</span><span class="sxs-lookup"><span data-stu-id="805fb-191">(#4995)</span></span>
- <span data-ttu-id="805fb-192">`pwsh -version`과 기본 제공 도움말 `pwsh.exe`이 다른 네이티브 도구와 일치하도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-192">Changed `pwsh -version` and built-in help for `pwsh.exe` to align with other native tools.</span></span> <span data-ttu-id="805fb-193">(#4958 & #4931) (@iSazonov에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-193">(#4958 & #4931) (Thanks @iSazonov)</span></span>
- <span data-ttu-id="805fb-194">`-File` 및 `-Command`에 대한 잘못된 인수 오류 메시지 및 Unix 표준과 일치하는 종료 코드 (#4573)</span><span class="sxs-lookup"><span data-stu-id="805fb-194">Invalid argument error messages for `-File` and `-Command` and exit codes consistent with Unix standards (#4573)</span></span>
- <span data-ttu-id="805fb-195">Windows에 `-WindowStyle` 매개 변수가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-195">Added `-WindowStyle` parameter on Windows.</span></span> <span data-ttu-id="805fb-196">(# 4573) 마찬가지로 Windows 이외의 플랫폼에서 패키지 기반 설치 업데이트가 적절한 업데이트입니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-196">(#4573) Similarly, package-based installations updates on non-Windows platforms are in-place updates.</span></span>

## <a name="backwards-compatibility-with-windows-powershell"></a><span data-ttu-id="805fb-197">이전 버전 Windows PowerShell과의 호환성</span><span class="sxs-lookup"><span data-stu-id="805fb-197">Backwards compatibility with Windows PowerShell</span></span>

<span data-ttu-id="805fb-198">PowerShell Core의 목표는 가능한 한 Windows PowerShell과 호환을 유지하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-198">The goal of PowerShell Core is to remain as compatible as possible with Windows PowerShell.</span></span>
<span data-ttu-id="805fb-199">PowerShell Core는 [.NET Standard][] 2.0을 사용하여 기존 .NET 어셈블리와 이진 호환성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-199">PowerShell Core uses [.NET Standard][] 2.0 to provide binary compatibility with existing .NET assemblies.</span></span>
<span data-ttu-id="805fb-200">많은 PowerShell 모듈이 이러한 어셈블리(종종 DLL)에 의존하기 때문에 .NET Standard는 .NET Core를 사용하여 계속 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-200">Many PowerShell modules depend on these assemblies (often times DLLs), so .NET Standard allows them to continue working with .NET Core.</span></span>
<span data-ttu-id="805fb-201">또한 PowerShell Core에는 일반적으로 전역 어셈블리 캐시가 디스크에 있는 것처럼 잘 알려진 폴더를 검색하여 .NET Framework DLL 종속성을 찾는 추론 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-201">PowerShell Core also includes a heuristic to look in well-known folders--like where the Global Assembly Cache typically resides on disk--to find .NET Framework DLL dependencies.</span></span>

<span data-ttu-id="805fb-202">[.NET Blog][], 이 [YouTube][] 비디오 및 GitHub의 이 [FAQ][]에서 .NET Standard에 대해 자세히 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-202">You can learn more about .NET Standard on the [.NET Blog][], in this [YouTube][] video, and via this [FAQ][] on GitHub.</span></span>

<span data-ttu-id="805fb-203">PowerShell 언어와 "기본 제공" 모듈(`Microsoft.PowerShell.Management`, `Microsoft.PowerShell.Utility` 등)이 Windows PowerShell에서와 동일하게 작동하도록 최선의 노력이 기울여 왔습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-203">Best efforts have been made to ensure that the PowerShell language and "built-in" modules (like `Microsoft.PowerShell.Management`, `Microsoft.PowerShell.Utility`, etc.) work the same as they do in Windows PowerShell.</span></span>
<span data-ttu-id="805fb-204">많은 경우 커뮤니티의 도움을 받아 해당 cmdlet에 새로운 기능과 버그 수정이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-204">In many cases, with the help of the community, we've added new capabilities and bug fixes to those cmdlets.</span></span>
<span data-ttu-id="805fb-205">경우에 따라 기본 .NET 계층의 종속성이 없어서 기능이 제거되었거나 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-205">In some cases, due to a missing dependency in underlying .NET layers, functionality was removed or is unavailable.</span></span>

<span data-ttu-id="805fb-206">Windows의 일부로 제공되는 대부분의 모듈(예: `DnsClient`, `Hyper-V`, `NetTCPIP`, `Storage` 등) 및 Azure 및 Office를 포함한 기타 Microsoft 제품은 *명시적으로* .NET Core로 아직 포팅되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-206">Most of the modules that ship as part of Windows (for example, `DnsClient`, `Hyper-V`, `NetTCPIP`, `Storage`, etc.) and other Microsoft products including Azure and Office have not been *explicitly* ported to .NET Core yet.</span></span>
<span data-ttu-id="805fb-207">PowerShell 팀은 이러한 제품 그룹 및 팀과 협력하여 기존 모듈의 유효성을 확인하고 PowerShell 코어로 포팅합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-207">The PowerShell team is working with these product groups and teams to validate and port their existing modules to PowerShell Core.</span></span>
<span data-ttu-id="805fb-208">.NET Standard 및 [CDXML][]을 사용하면 이러한 기존의 Windows PowerShell 모듈 중 상당수가 PowerShell Core에서 작동하는 것처럼 보이지만, 공식적으로 유효성이 검사되지 않았을 뿐만 아니라 공식적으로 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-208">With .NET Standard and [CDXML][], many of these traditional Windows PowerShell modules do seem to work in PowerShell Core, but they have not been formally validated, and they are not formally supported.</span></span>

<span data-ttu-id="805fb-209">[`WindowsPSModulePath`][windowspsmodulepath] 모듈을 설치하면 Windows PowerShell `PSModulePath`을 PowerShell Core `PSModulePath`에 추가하여 Windows PowerShell 모듈을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-209">By installing the [`WindowsPSModulePath`][windowspsmodulepath] module, you can use Windows PowerShell modules by appending the Windows PowerShell `PSModulePath` to your PowerShell Core `PSModulePath`.</span></span>

<span data-ttu-id="805fb-210">먼저 PowerShell 갤러리에서 `WindowsPSModulePath` 모듈을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-210">First, install the `WindowsPSModulePath` module from the PowerShell Gallery:</span></span>

```powershell
# Add `-Scope CurrentUser` if you're installing as non-admin 
Install-Module WindowsPSModulePath -Force
```

<span data-ttu-id="805fb-211">이 모듈이 설치되면, `Add-WindowsPSModulePath` cmdlet을 실행하여 Windows PowerShell `PSModulePath`를 PowerShell Core에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-211">After installing this module, run the `Add-WindowsPSModulePath` cmdlet to add the Windows PowerShell `PSModulePath` to PowerShell Core:</span></span>

```powershell
# Add this line to your profile if you always want Windows PowerShell PSModulePath
Add-WindowsPSModulePath
```

## <a name="docker-support"></a><span data-ttu-id="805fb-212">Docker 지원</span><span class="sxs-lookup"><span data-stu-id="805fb-212">Docker support</span></span>

<span data-ttu-id="805fb-213">PowerShell Core는 지원하는 모든 주요 플랫폼(여러 Linux 배포판, Windows Server Core 및 Nano 서버 포함)에 대한 Docker 컨테이너 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-213">PowerShell Core adds support for Docker containers for all the major platforms we support (including multiple Linux distros, Windows Server Core, and Nano Server).</span></span>

<span data-ttu-id="805fb-214">전체 목록을 보려면 Docker Hub][docker-hub]의 [`microsoft/powershell`에 있는 태그를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-214">For a complete list, check out the tags on [`microsoft/powershell` on Docker Hub][docker-hub].</span></span>
<span data-ttu-id="805fb-215">Docker 및 PowerShell Core에 대한 자세한 내용은 GitHub의 [Docker][]를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="805fb-215">For more information on Docker and PowerShell Core, see [Docker][] on GitHub.</span></span>

## <a name="ssh-based-powershell-remoting"></a><span data-ttu-id="805fb-216">SSH 기반 PowerShell 원격</span><span class="sxs-lookup"><span data-stu-id="805fb-216">SSH-based PowerShell Remoting</span></span>

<span data-ttu-id="805fb-217">PowerShell Remoting Protocol(PSRP)은 이제 기존 WinRM 기반 PSRP 외에도 Secure Shell(SSH) 프로토콜과도 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-217">The PowerShell Remoting Protocol (PSRP) now works with the Secure Shell (SSH) protocol in addition to the traditional WinRM-based PSRP.</span></span>

<span data-ttu-id="805fb-218">즉, `Enter-PSSession` 및 `New-PSSession`와 같은 cmdlet을 사용하고 SSH를 사용하여 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-218">This means that you can use cmdlets like `Enter-PSSession` and `New-PSSession` and authenticate using SSH.</span></span>
<span data-ttu-id="805fb-219">OpenSSH 기반 SSH 서버를 사용하여 PowerShell을 서브 시스템으로 등록하면, 기존의 `PSSession` 의미 체계와 함께 기존 SSH 기반 인증 메커니즘(암호 또는 개인 키 등)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-219">All you have to do is register PowerShell as a subsystem with an OpenSSH-based SSH server, and you can use your existing SSH-based authenticate mechanisms (like passwords or private keys) with the traditional `PSSession` semantics.</span></span>

<span data-ttu-id="805fb-220">SSH 기반 원격 구성 및 사용에 대한 자세한 내용은 [SSH를 통한 PowerShell 원격][ssh-remoting]을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="805fb-220">For more information on configuring and using SSH-based remoting, see [PowerShell Remoting over SSH][ssh-remoting].</span></span>

## <a name="default-encoding-is-utf-8-without-a-bom"></a><span data-ttu-id="805fb-221">기본 인코딩은 BOM이 없는 UTF-8입니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-221">Default encoding is UTF-8 without a BOM</span></span>

<span data-ttu-id="805fb-222">과거에는 `Get-Content`, `Set-Content`와 같은 Windows PowerShell cmdlet에서 ASCII 및 UTF-16 등 다른 인코딩을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-222">In the past, Windows PowerShell cmdlets like `Get-Content`, `Set-Content` used different encodings, such as ASCII and UTF-16.</span></span>
<span data-ttu-id="805fb-223">인코딩 기본값을 변경하면 인코딩을 지정하지 않고 cmdlet을 혼합할 때 문제가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-223">The variance in encoding defaults created problems when mixing cmdlets without specifying an encoding.</span></span>

<span data-ttu-id="805fb-224">Windows 이외의 플랫폼에서는 텍스트 파일의 기본 인코딩으로 BOM(Byte Order Mark)이 없는 UTF-8을 일반적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-224">Non-Windows platforms traditionally use UTF-8 without a Byte Order Mark (BOM) as the default encoding for text files.</span></span>
<span data-ttu-id="805fb-225">점점 많은 Windows 응용 프로그램과 도구가 UTF-16에서 BOM 없는 UTF-8 인코딩으로 이동하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-225">More Windows applications and tools are moving away from UTF-16 and towards BOM-less UTF-8 encoding.</span></span>
<span data-ttu-id="805fb-226">PowerShell Core는 보다 넓은 에코시스템을 준수하도록 기본 인코딩을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-226">PowerShell Core changes the default encoding to conform with the broader ecosystems.</span></span>

<span data-ttu-id="805fb-227">즉, `-Encoding` 매개 변수를 사용하는 모든 기본 제공 cmdlet은 기본적으로 `UTF8NoBOM` 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-227">This means that all built-in cmdlets that use the `-Encoding` parameter use the `UTF8NoBOM` value by default.</span></span>
<span data-ttu-id="805fb-228">다음 cmdlet가 이러한 변경에 의해 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-228">The following cmdlets are affected by this change:</span></span>

- <span data-ttu-id="805fb-229">Add-Content</span><span class="sxs-lookup"><span data-stu-id="805fb-229">Add-Content</span></span>
- <span data-ttu-id="805fb-230">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="805fb-230">Export-Clixml</span></span>
- <span data-ttu-id="805fb-231">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="805fb-231">Export-Csv</span></span>
- <span data-ttu-id="805fb-232">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="805fb-232">Export-PSSession</span></span>
- <span data-ttu-id="805fb-233">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="805fb-233">Format-Hex</span></span>
- <span data-ttu-id="805fb-234">Get-Content</span><span class="sxs-lookup"><span data-stu-id="805fb-234">Get-Content</span></span>
- <span data-ttu-id="805fb-235">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="805fb-235">Import-Csv</span></span>
- <span data-ttu-id="805fb-236">New-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="805fb-236">New-ModuleManifest</span></span>
- <span data-ttu-id="805fb-237">Out-File</span><span class="sxs-lookup"><span data-stu-id="805fb-237">Out-File</span></span>
- <span data-ttu-id="805fb-238">Select-String</span><span class="sxs-lookup"><span data-stu-id="805fb-238">Select-String</span></span>
- <span data-ttu-id="805fb-239">Send-MailMessage</span><span class="sxs-lookup"><span data-stu-id="805fb-239">Send-MailMessage</span></span>
- <span data-ttu-id="805fb-240">Set-Content</span><span class="sxs-lookup"><span data-stu-id="805fb-240">Set-Content</span></span>

<span data-ttu-id="805fb-241">이러한 cmdlet도 업데이트되어 `-Encoding` 매개 변수가 보편적으로 `System.Text.Encoding`을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-241">These cmdlets have also been updated so that the `-Encoding` parameter universally accepts `System.Text.Encoding`.</span></span>

<span data-ttu-id="805fb-242">`$OutputEncoding`의 기본값도 UTF-8로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-242">The default value of `$OutputEncoding` has also been changed to UTF-8.</span></span>

<span data-ttu-id="805fb-243">가장 좋은 방법은 `-Encoding` 매개 변수를 사용하여 스크립트에서 인코딩을 명시적으로 설정하여 플랫폼 간의 결정적 동작을 생성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-243">As a best practice, you should explicitly set encodings in scripts using the `-Encoding` parameter to produce deterministic behavior across platforms.</span></span>

## <a name="support-backgrounding-of-pipelines-with-ampersand--3360"></a><span data-ttu-id="805fb-244">앰퍼샌드(`&`)를 사용하여 파이프라인의 백그라운드 지원 (#3360)</span><span class="sxs-lookup"><span data-stu-id="805fb-244">Support backgrounding of pipelines with ampersand (`&`) (#3360)</span></span>

<span data-ttu-id="805fb-245">파이프라인 끝에 `&`을 배치하면 파이프라인이 PowerShell 작업으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-245">Putting `&` at the end of a pipeline causes the pipeline to be run as a PowerShell job.</span></span>
<span data-ttu-id="805fb-246">파이프라인이 백그라운드로 설정되면 작업 개체가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-246">When a pipeline is backgrounded, a job object is returned.</span></span>
<span data-ttu-id="805fb-247">일단 파이프라인이 작업으로 실행되면 모든 표준 `*-Job` cmdlet을 사용하여 작업을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-247">Once the pipeline is running as a job, all of the standard `*-Job` cmdlets can be used to manage the job.</span></span>
<span data-ttu-id="805fb-248">파이프라인에서 사용되는 변수(프로세스별 변수 무시)는 작업에 자동으로 복사되므로 `Copy-Item $foo $bar &`가 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-248">Variables (ignoring process-specific variables) used in the pipeline are automatically copied to the job so `Copy-Item $foo $bar &` just works.</span></span>
<span data-ttu-id="805fb-249">작업은 또한 사용자의 홈 디렉터리가 아닌 현재 디렉터리에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-249">The job is also run in the current directory instead of the user's home directory.</span></span>
<span data-ttu-id="805fb-250">PowerShell 작업에 대한 자세한 내용은 [about_Jobs](https://msdn.microsoft.com/powershell/reference/6/about/about_jobs)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="805fb-250">For more information about PowerShell jobs, see [about_Jobs](https://msdn.microsoft.com/powershell/reference/6/about/about_jobs).</span></span>

## <a name="semantic-versioning"></a><span data-ttu-id="805fb-251">유의적 버전 사용</span><span class="sxs-lookup"><span data-stu-id="805fb-251">Semantic versioning</span></span>

- <span data-ttu-id="805fb-252">`SemVer 2.0`와 호환되도록 `SemanticVersion`을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-252">Made `SemanticVersion` compatible with `SemVer 2.0`.</span></span> <span data-ttu-id="805fb-253">(#5037) (@iSazonov에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-253">(#5037) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="805fb-254">SemVer와 일치하도록 `New-ModuleManifest`의 기본값 `ModuleVersion`을 `0.0.1`로 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-254">Changed default `ModuleVersion` in `New-ModuleManifest` to `0.0.1` to align with SemVer.</span></span> <span data-ttu-id="805fb-255">(#4842) (@LDSpits에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-255">(#4842) (Thanks @LDSpits)</span></span>
- <span data-ttu-id="805fb-256">`semver`을 `System.Management.Automation.SemanticVersion`의 유형 가속기로 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-256">Added `semver` as a type accelerator for `System.Management.Automation.SemanticVersion`.</span></span> <span data-ttu-id="805fb-257">(#4142) (@oising에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-257">(#4142) (Thanks to @oising!)</span></span>
- <span data-ttu-id="805fb-258">`Major` 및 `Minor` 버전 값으로만 구성된 `SemanticVersion` 인스턴스와 `Version` 인스턴스 간의 비교가 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-258">Enabled comparison between a `SemanticVersion` instance and a `Version` instance that is constructed only with `Major` and `Minor` version values.</span></span>

## <a name="language-updates"></a><span data-ttu-id="805fb-259">언어 업데이트</span><span class="sxs-lookup"><span data-stu-id="805fb-259">Language updates</span></span>

- <span data-ttu-id="805fb-260">사용자가 유니코드 문자를 인수, 문자열 또는 변수 이름으로 사용할 수 있도록 유니코드 이스케이프 구문 분석을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-260">Implement Unicode escape parsing so that users can use Unicode characters as arguments, strings, or variable names.</span></span> <span data-ttu-id="805fb-261">(#3958) (@rkeithhill에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-261">(#3958) (Thanks to @rkeithhill!)</span></span>
- <span data-ttu-id="805fb-262">ESC: `` `e``를 위한 새로운 이스케이프 문자 추가됨</span><span class="sxs-lookup"><span data-stu-id="805fb-262">Added new escape character for ESC: `` `e``</span></span>
- <span data-ttu-id="805fb-263">열거형을 문자열로 변환하기 위한 지원 추가됨 (#4318) (@KirkMunro에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-263">Added support for converting enums to string (#4318) (Thanks @KirkMunro)</span></span>
- <span data-ttu-id="805fb-264">단일 요소 배열을 일반 컬렉션에 캐스팅되는 현상 수정됨</span><span class="sxs-lookup"><span data-stu-id="805fb-264">Fixed casting single element array to a generic collection.</span></span> <span data-ttu-id="805fb-265">(#3170)</span><span class="sxs-lookup"><span data-stu-id="805fb-265">(#3170)</span></span>
- <span data-ttu-id="805fb-266">문자 범위 오버로드가 `..` 연산자에 추가되어 `'a'..'z'`는 'a'에서 'z'로 문자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-266">Added character range overload to the `..` operator, so `'a'..'z'` returns characters from 'a' to 'z'.</span></span> <span data-ttu-id="805fb-267">(#5026) (@IISResetMe에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-267">(#5026) (Thanks @IISResetMe!)</span></span>
- <span data-ttu-id="805fb-268">읽기 전용 변수를 덮어 쓰지 않도록 변수 할당 수정됨</span><span class="sxs-lookup"><span data-stu-id="805fb-268">Fixed variable assignment to not overwrite read-only variables</span></span>
- <span data-ttu-id="805fb-269">스크립트 cmdlet를 도팅할 때 자동 변수의 로컬을 'DottedScopes'에 밀어넣기 (#4709)</span><span class="sxs-lookup"><span data-stu-id="805fb-269">Push locals of automatic variables to 'DottedScopes' when dotting script cmdlets (#4709)</span></span>
- <span data-ttu-id="805fb-270">분할 연산자에서 'Singleline, Multiline' 옵션 사용 가능 (#4721) (@iSazonov에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-270">Enable use of 'Singleline, Multiline' option in split operator (#4721) (Thanks @iSazonov)</span></span>

## <a name="engine-updates"></a><span data-ttu-id="805fb-271">엔진 업데이트</span><span class="sxs-lookup"><span data-stu-id="805fb-271">Engine updates</span></span>

- <span data-ttu-id="805fb-272">`$PSVersionTable`에는 다음과 같이 4개의 새로운 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-272">`$PSVersionTable` has four new properties:</span></span>
  - <span data-ttu-id="805fb-273">`PSEdition`: PowerShell Core에서는 `Core`로 설정되고 Windows PowerShell에서는 `Desktop`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-273">`PSEdition`: This is set to `Core` on PowerShell Core and `Desktop` on Windows PowerShell</span></span>
  - <span data-ttu-id="805fb-274">`GitCommitId`: PowerShell이 빌드된 Git 분기 또는 태그의 Git 커밋 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-274">`GitCommitId`: This is the Git commit ID of the Git branch or tag where PowerShell was built.</span></span>
    <span data-ttu-id="805fb-275">릴리스된 빌드에서는 `PSVersion`과 동일할 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-275">On released builds, it will likely be the same as `PSVersion`.</span></span>
  - <span data-ttu-id="805fb-276">`OS`: `[System.Runtime.InteropServices.RuntimeInformation]::OSDescription`에 의해 반환된 OS 버전 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-276">`OS`: This is an OS version string returned by `[System.Runtime.InteropServices.RuntimeInformation]::OSDescription`</span></span>
  - <span data-ttu-id="805fb-277">`Platform`: `[System.Environment]::OSVersion.Platform`에 의해 반환됩니다. Windows에서는 `Win32NT`, macOS에서는 `MacOSX`, Linux에서는 `Unix`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-277">`Platform`: This is returned by `[System.Environment]::OSVersion.Platform` It is set to `Win32NT` on Windows, `MacOSX` on macOS, and `Unix` on Linux.</span></span>
- <span data-ttu-id="805fb-278">`$PSVersionTable`에서 `BuildVersion` 속성이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-278">Removed the `BuildVersion` property from `$PSVersionTable`.</span></span>
  <span data-ttu-id="805fb-279">이 속성은 Windows 빌드 버전과 강하게 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-279">This property was strongly tied to the Windows build version.</span></span>
  <span data-ttu-id="805fb-280">대신 `GitCommitId`를 사용하여 PowerShell Core의 정확한 빌드 버전을 검색하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-280">Instead, we recommend that you use `GitCommitId` to retrieve the exact build version of PowerShell Core.</span></span> <span data-ttu-id="805fb-281">(#3877) (@iSazonov에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-281">(#3877) (Thanks to @iSazonov!)</span></span>
- <span data-ttu-id="805fb-282">`$PSVersionTable`에서 `ClrVersion` 속성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-282">Remove `ClrVersion` property from `$PSVersionTable`.</span></span>
  <span data-ttu-id="805fb-283">이 속성은 .NET Core와는 관련이 없으며 PowerShell에 적용할 수 없는 특정 레거시 용도로만 .NET Core에 유지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-283">This property is irrelevant for .NET Core, and was only preserved in .NET Core for specific legacy purposes that are inapplicable to PowerShell.</span></span>
- <span data-ttu-id="805fb-284">PowerShell이 주어진 OS(`$IsWindows`, `$IsMacOs` 및 `$IsLinux`)에서 실행 중인지 여부를 결정하는 세 가지 새로운 자동 변수가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-284">Added three new automatic variables to determine whether PowerShell is running in a given OS: `$IsWindows`, `$IsMacOs`, and `$IsLinux`.</span></span>
- <span data-ttu-id="805fb-285">PowerShell Core 배너에 `GitCommitId`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-285">Add `GitCommitId` to PowerShell Core banner.</span></span>
  <span data-ttu-id="805fb-286">이제 버전을 얻기 위해 PowerShell을 시작하자마자 `$PSVersionTable`을 실행할 필요가 없습니다!</span><span class="sxs-lookup"><span data-stu-id="805fb-286">Now you don't have to run `$PSVersionTable` as soon as you start PowerShell to get the version!</span></span> <span data-ttu-id="805fb-287">(#3916) (@iSazonov에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-287">(#3916) (Thanks to @iSazonov!)</span></span>
- <span data-ttu-id="805fb-288">`$PSHome`에 `PowerShellProperties.json`이라는 JSON 구성 파일을 추가하여 시작 시간(예: `ExecutionPolicy`) 이전에 필요한 일부 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-288">Add a JSON config file called `PowerShellProperties.json` in `$PSHome` to store some settings required before startup time (e.g. `ExecutionPolicy`).</span></span>
- <span data-ttu-id="805fb-289">Windows EXE를 실행할 때 파이프라인을 차단하지 않음</span><span class="sxs-lookup"><span data-stu-id="805fb-289">Don't block pipeline when running Windows EXE's</span></span>
- <span data-ttu-id="805fb-290">COM 컬렉션의 열거를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-290">Enabled enumeration of COM collections.</span></span> <span data-ttu-id="805fb-291">(#4553)</span><span class="sxs-lookup"><span data-stu-id="805fb-291">(#4553)</span></span>

## <a name="cmdlet-updates"></a><span data-ttu-id="805fb-292">cmdlet 업데이트</span><span class="sxs-lookup"><span data-stu-id="805fb-292">Cmdlet updates</span></span>

### <a name="new-cmdlets"></a><span data-ttu-id="805fb-293">새로운 cmdlet</span><span class="sxs-lookup"><span data-stu-id="805fb-293">New cmdlets</span></span>

- <span data-ttu-id="805fb-294">`Get-Uptime`을 `Microsoft.PowerShell.Utility`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-294">Add `Get-Uptime` to `Microsoft.PowerShell.Utility`.</span></span>
- <span data-ttu-id="805fb-295">`Remove-Alias` 명령을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-295">Add `Remove-Alias` Command.</span></span> <span data-ttu-id="805fb-296">(#5143) (@PowershellNinja에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-296">(#5143) (Thanks @PowershellNinja!)</span></span>
- <span data-ttu-id="805fb-297">`Remove-Service`를 관리 모듈에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-297">Add `Remove-Service` to Management module.</span></span> <span data-ttu-id="805fb-298">(#4858) (@joandrsn에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-298">(#4858) (Thanks @joandrsn!)</span></span>

### <a name="web-cmdlets"></a><span data-ttu-id="805fb-299">웹 cmdlet</span><span class="sxs-lookup"><span data-stu-id="805fb-299">Web cmdlets</span></span>

- <span data-ttu-id="805fb-300">웹 cmdlet에 대한 인증서 인증 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-300">Add certificate authentication support for web cmdlets.</span></span> <span data-ttu-id="805fb-301">(#4646) (@markekraus에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-301">(#4646) (Thanks @markekraus)</span></span>
- <span data-ttu-id="805fb-302">웹 cmdlet에 콘텐츠 헤더 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-302">Add support for content headers to web cmdlets.</span></span> <span data-ttu-id="805fb-303">(#4494 & #4640) (@markekraus에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-303">(#4494 & #4640) (Thanks @markekraus)</span></span>
- <span data-ttu-id="805fb-304">웹 cmdlet에 다중 링크 헤더 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-304">Add multiple link header support to Web Cmdlets.</span></span> <span data-ttu-id="805fb-305">(#5265) (@markekraus에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-305">(#5265) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="805fb-306">웹 cmdlet의 링크 헤더 페이지 매김 지원 (#3828)</span><span class="sxs-lookup"><span data-stu-id="805fb-306">Support Link header pagination in web cmdlets (#3828)</span></span>
  - <span data-ttu-id="805fb-307">`Invoke-WebRequest`의 경우, 응답에 링크 헤더가 포함될 때 URL 및 `rel` 특성을 나타내는 사전으로 RelationLink 속성을 만들고 개발자가 쉽게 사용할 수 있도록 URL이 절대적인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-307">For `Invoke-WebRequest`, when the response includes a Link header we create a RelationLink property as a Dictionary representing the URLs and `rel` attributes and ensure the URLs are absolute to make it easier for the developer to use.</span></span>
  - <span data-ttu-id="805fb-308">`Invoke-RestMethod`의 경우, 응답에 링크 헤더가 포함될 때 더 이상 존재하지 않거나 선택적 `-MaximumFollowRelLink` 매개 변수 값에 도달할 때까지 자동으로 `next` `rel` 링크를 따라가는 `-FollowRelLink` 스위치가 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-308">For `Invoke-RestMethod`, when the response includes a Link header we expose a `-FollowRelLink` switch to automatically follow `next` `rel` links until they no longer exist or once we hit the optional `-MaximumFollowRelLink` parameter value.</span></span>
- <span data-ttu-id="805fb-309">웹 cmdlet에 `-CustomMethod` 매개 변수를 추가하여 비표준 메서드 동사를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-309">Add `-CustomMethod` parameter to web cmdlets to allow for non-standard method verbs.</span></span> <span data-ttu-id="805fb-310">(#3142) (@Lee303에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-310">(#3142) (Thanks to @Lee303!)</span></span>
- <span data-ttu-id="805fb-311">웹 cmdlet에 `SslProtocol` 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-311">Add `SslProtocol` support to Web Cmdlets.</span></span> <span data-ttu-id="805fb-312">(#5329) (@markekraus에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-312">(#5329) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="805fb-313">웹 cmdlet에 Multipart 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-313">Add Multipart support to web cmdlets.</span></span> <span data-ttu-id="805fb-314">(#4782) (@markekraus에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-314">(#4782) (Thanks @markekraus)</span></span>
- <span data-ttu-id="805fb-315">웹 cmdlet에 `-NoProxy`를 추가하여 시스템 수준의 프록시 설정을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-315">Add `-NoProxy` to web cmdlets so that they ignore the system-wide proxy setting.</span></span> <span data-ttu-id="805fb-316">(#3447) (@TheFlyingCorpse에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-316">(#3447) (Thanks to @TheFlyingCorpse!)</span></span>
- <span data-ttu-id="805fb-317">웹 cmdlet의 사용자 에이전트가 이제 OS 플랫폼을 보고합니다. (#4937) (@LDSpits에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-317">User Agent of Web Cmdlets now reports the OS platform (#4937) (Thanks @LDSpits)</span></span>
- <span data-ttu-id="805fb-318">웹 cmdlet에 `-SkipHeaderValidation` 스위치를 추가하여 헤더 값의 유효성을 검사하지 않고 헤더 추가를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-318">Add `-SkipHeaderValidation` switch to web cmdlets to support adding headers without validating the header value.</span></span> <span data-ttu-id="805fb-319">(#4085)</span><span class="sxs-lookup"><span data-stu-id="805fb-319">(#4085)</span></span>
- <span data-ttu-id="805fb-320">필요한 경우 웹 cmdlet이 서버의 HTTPS 인증서의 유효성을 검사하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-320">Enable web cmdlets to not validate the HTTPS certificate of the server if required.</span></span>
- <span data-ttu-id="805fb-321">웹 cmdlet에 인증 매개 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-321">Add authentication parameters to web cmdlets.</span></span> <span data-ttu-id="805fb-322">(#5052) (@markekraus에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-322">(#5052) (Thanks @markekraus)</span></span>
  - <span data-ttu-id="805fb-323">기본, OAuth 및 전달자의 세 가지 옵션을 제공하는 `-Authentication`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-323">Add `-Authentication` that provides three options: Basic, OAuth, and Bearer.</span></span>
  - <span data-ttu-id="805fb-324">`-Token`을 추가하여 OAuth 및 전달자 옵션에 대한 전달자 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-324">Add `-Token` to get the bearer token for OAuth and Bearer options.</span></span>
  - <span data-ttu-id="805fb-325">HTTPS 이외의 전송 체계에 제공된 인증을 생략하려면 `-AllowUnencryptedAuthentication`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-325">Add `-AllowUnencryptedAuthentication` to bypass authentication that is provided for any transport scheme other than HTTPS.</span></span>
- <span data-ttu-id="805fb-326">응답 헤더 캡처를 사용하려면 `-ResponseHeadersVariable`을 `Invoke-RestMethod`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-326">Add `-ResponseHeadersVariable` to `Invoke-RestMethod` to enable the capture of response headers.</span></span> <span data-ttu-id="805fb-327">(#4888) (@markekraus에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-327">(#4888) (Thanks @markekraus)</span></span>
- <span data-ttu-id="805fb-328">응답 상태 코드가 성공적이지 않은 경우 예외에 HTTP 응답을 포함하도록 웹 cmdlet을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-328">Fix web cmdlets to include the HTTP response in the exception when the response status code is not success.</span></span> <span data-ttu-id="805fb-329">(#3201)</span><span class="sxs-lookup"><span data-stu-id="805fb-329">(#3201)</span></span>
- <span data-ttu-id="805fb-330">웹 cmdlet `UserAgent`를 `WindowsPowerShell`에서 `PowerShell`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-330">Change web cmdlets `UserAgent` from `WindowsPowerShell` to `PowerShell`.</span></span> <span data-ttu-id="805fb-331">(#4914) (@markekraus에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-331">(#4914) (Thanks @markekraus)</span></span>
- <span data-ttu-id="805fb-332">명시적 `ContentType` 검색을 `Invoke-RestMethod`에 추가합니다. (#4692)</span><span class="sxs-lookup"><span data-stu-id="805fb-332">Add explicit `ContentType` detection to `Invoke-RestMethod` (#4692)</span></span>
- <span data-ttu-id="805fb-333">비표준 사용자 에이전트 헤더에서 작동하도록 웹 cmdlet `-SkipHeaderValidation`을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-333">Fix web cmdlets `-SkipHeaderValidation` to work with non-standard User-Agent headers.</span></span> <span data-ttu-id="805fb-334">(#4479 & #4512) (@markekraus에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-334">(#4479 & #4512) (Thanks @markekraus)</span></span>

### <a name="json-cmdlets"></a><span data-ttu-id="805fb-335">JSON cmdlet</span><span class="sxs-lookup"><span data-stu-id="805fb-335">JSON cmdlets</span></span>

- <span data-ttu-id="805fb-336">`-AsHashtable`을 `ConvertFrom-Json`에 추가하여 `Hashtable`을 대신 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-336">Add `-AsHashtable` to `ConvertFrom-Json` to return a `Hashtable` instead.</span></span> <span data-ttu-id="805fb-337">(#5043) (@bergmeister에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-337">(#5043) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="805fb-338">`ConvertTo-Json` 출력과 함께 더 보기 좋은 포맷터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-338">Use prettier formatter with `ConvertTo-Json` output.</span></span> <span data-ttu-id="805fb-339">(#2787) (@kittholland에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-339">(#2787) (Thanks to @kittholland!)</span></span>
- <span data-ttu-id="805fb-340">`Jobject` 직렬화 지원을 `ConvertTo-Json`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-340">Add `Jobject` serialization support to `ConvertTo-Json`.</span></span> <span data-ttu-id="805fb-341">(#5141)</span><span class="sxs-lookup"><span data-stu-id="805fb-341">(#5141)</span></span>
- <span data-ttu-id="805fb-342">`ConvertFrom-Json`을 수정하여 완전한 JSON 문자열을 함께 구성하는 파이프라인에서 문자열 배열을 역직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-342">Fix `ConvertFrom-Json` to deserialize an array of strings from the pipeline that together construct a complete JSON string.</span></span>
  <span data-ttu-id="805fb-343">이렇게 하면 줄 바꿈이 JSON 구문 분석을 중단시키는 일부 경우가 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-343">This fixes some cases where newlines would break JSON parsing.</span></span> <span data-ttu-id="805fb-344">(#3823)</span><span class="sxs-lookup"><span data-stu-id="805fb-344">(#3823)</span></span>
- <span data-ttu-id="805fb-345">`System.Array`에 대해 정의된 `AliasProperty "Count"`를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-345">Remove the `AliasProperty "Count"` defined for `System.Array`.</span></span>
  <span data-ttu-id="805fb-346">이렇게 하면 일부 `ConvertFrom-Json` 출력에서 불필요한 `Count` 속성이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-346">This removes the extraneous `Count` property on some `ConvertFrom-Json` output.</span></span> <span data-ttu-id="805fb-347">(#3231) (@PetSerAl에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-347">(#3231) (Thanks to @PetSerAl!)</span></span>

### <a name="csv-cmdlets"></a><span data-ttu-id="805fb-348">CSV cmdlet</span><span class="sxs-lookup"><span data-stu-id="805fb-348">CSV cmdlets</span></span>

- <span data-ttu-id="805fb-349">`Import-Csv` 및 `ConvertFrom-Csv`에 대한 `PSTypeName` 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-349">Add `PSTypeName` Support for `Import-Csv` and `ConvertFrom-Csv`.</span></span> <span data-ttu-id="805fb-350">(#5389) (@markekraus에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-350">(#5389) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="805fb-351">`Import-Csv`를 `CR`, `LF` 및 `CRLF`를 줄 구분 기호로 지원하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-351">Make `Import-Csv` support `CR`, `LF`, and `CRLF` as line delimiters.</span></span> <span data-ttu-id="805fb-352">(#5363) (@iSazonov에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-352">(#5363) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="805fb-353">`-NoTypeInformation`을 `Export-Csv` 및 `ConvertTo-Csv`의 기본값으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-353">Make `-NoTypeInformation` the default on `Export-Csv` and `ConvertTo-Csv`.</span></span> <span data-ttu-id="805fb-354">(#5164) (@markekraus에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-354">(#5164) (Thanks @markekraus)</span></span>

### <a name="service-cmdlets"></a><span data-ttu-id="805fb-355">서비스 cmdlet</span><span class="sxs-lookup"><span data-stu-id="805fb-355">Service cmdlets</span></span>

- <span data-ttu-id="805fb-356">`Get-Service`에 의해 반환된 `ServiceController` 객체에 속성 `UserName`, `Description`, `DelayedAutoStart`, `BinaryPathName` 및 `StartupType`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-356">Add properties `UserName`, `Description`, `DelayedAutoStart`, `BinaryPathName`, and `StartupType` to the `ServiceController` objects returned by `Get-Service`.</span></span> <span data-ttu-id="805fb-357">(#4907) (@joandrsn에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-357">(#4907) (Thanks @joandrsn)</span></span>
- <span data-ttu-id="805fb-358">`Set-Service` 명령에서 자격 증명을 설정하는 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-358">Add functionality to set credentials on `Set-Service` command.</span></span> <span data-ttu-id="805fb-359">(#4844) (@joandrsn에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-359">(#4844) (Thanks @joandrsn)</span></span>

### <a name="other-cmdlets"></a><span data-ttu-id="805fb-360">기타 cmdlet</span><span class="sxs-lookup"><span data-stu-id="805fb-360">Other cmdlets</span></span>

- <span data-ttu-id="805fb-361">링크 루프를 확인하고 필요 시 symlinks를 통과하는 `-FollowSymlink`라는 `Get-ChildItem`에 매개 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-361">Add a parameter to `Get-ChildItem` called `-FollowSymlink` that traverses symlinks on demand, with checks for link loops.</span></span> <span data-ttu-id="805fb-362">(#4020)</span><span class="sxs-lookup"><span data-stu-id="805fb-362">(#4020)</span></span>
- <span data-ttu-id="805fb-363">`Add-Type`을 업데이트하여 `CSharpVersion7`을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-363">Update `Add-Type` to support `CSharpVersion7`.</span></span> <span data-ttu-id="805fb-364">(#3933) (@iSazonov에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-364">(#3933) (Thanks to @iSazonov)</span></span>
- <span data-ttu-id="805fb-365">더 나은 해결책을 찾을 때까지 지원되지 않는 API를 사용하기 때문에 `Microsoft.PowerShell.LocalAccounts` 모듈을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-365">Remove the `Microsoft.PowerShell.LocalAccounts` module due to the use of unsupported APIs until a better solution is found.</span></span> <span data-ttu-id="805fb-366">(#4302)</span><span class="sxs-lookup"><span data-stu-id="805fb-366">(#4302)</span></span>
- <span data-ttu-id="805fb-367">더 나은 해결책을 찾을 때까지 지원되지 않는 API를 사용하기 때문에 `Microsoft.PowerShell.Diagnostics`에 있는 `*-Counter` cmdlet을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-367">Remove the `*-Counter` cmdlets in `Microsoft.PowerShell.Diagnostics` due to the use of unsupported APIs until a better solution is found.</span></span> <span data-ttu-id="805fb-368">(#4303)</span><span class="sxs-lookup"><span data-stu-id="805fb-368">(#4303)</span></span>
- <span data-ttu-id="805fb-369">`Invoke-Item -Path <folder>`에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-369">Add support for `Invoke-Item -Path <folder>`.</span></span> <span data-ttu-id="805fb-370">(#4262)</span><span class="sxs-lookup"><span data-stu-id="805fb-370">(#4262)</span></span>
- <span data-ttu-id="805fb-371">`-Extension` 및 `-LeafBase` 스위치를 `Split-Path`에 추가하면 파일 이름 확장자와 파일 이름의 나머지 사이에 경로를 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-371">Add `-Extension` and `-LeafBase` switches to `Split-Path` so that you can split paths between the filename extension and the rest of the filename.</span></span> <span data-ttu-id="805fb-372">(#2721) (@powercode에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-372">(#2721) (Thanks to @powercode!)</span></span>
- <span data-ttu-id="805fb-373">위쪽/아래쪽 N 정렬을 위해 매개 변수 `-Top` 및 `-Bottom`을 `Sort-Object`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-373">Add parameters `-Top` and `-Bottom` to `Sort-Object` for Top/Bottom N sort</span></span>
- <span data-ttu-id="805fb-374">`CodeProperty "Parent"`를 `System.Diagnostics.Process`에 추가하여 프로세스의 상위 프로세스를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-374">Expose a process' parent process by adding the `CodeProperty "Parent"` to `System.Diagnostics.Process`.</span></span> <span data-ttu-id="805fb-375">(#2850) (@powercode에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-375">(#2850) (Thanks to @powercode!)</span></span>
- <span data-ttu-id="805fb-376">`Get-Process`의 메모리 열에 KB 대신 MB를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-376">Use MB instead of KB for memory columns of `Get-Process`</span></span>
- <span data-ttu-id="805fb-377">`Out-String`을 위해 `-NoNewLine` 스위치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-377">Add `-NoNewLine` switch for `Out-String`.</span></span> <span data-ttu-id="805fb-378">(#5056) (@raghav710에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-378">(#5056) (Thanks @raghav710)</span></span>
- <span data-ttu-id="805fb-379">`Move-Item` cmdlet은 `-Include`, `-Exclude` 및 `-Filter` 매개 변수를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-379">`Move-Item` cmdlet honors `-Include`, `-Exclude`, and `-Filter` parameters.</span></span> <span data-ttu-id="805fb-380">(#3878)</span><span class="sxs-lookup"><span data-stu-id="805fb-380">(#3878)</span></span>
- <span data-ttu-id="805fb-381">`Remove-Item`의 레지스트리 경로에 사용되도록 `*`를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-381">Allow `*` to be used in registry path for `Remove-Item`.</span></span> <span data-ttu-id="805fb-382">(#4866)</span><span class="sxs-lookup"><span data-stu-id="805fb-382">(#4866)</span></span>
- <span data-ttu-id="805fb-383">`-Title`을 `Get-Credential`에 추가하고 플랫폼 간 프롬프트 경험을 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-383">Add `-Title` to `Get-Credential` and unify the prompt experience across platforms.</span></span>
- <span data-ttu-id="805fb-384">`-TimeOut` 매개 변수를 `Test-Connection`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-384">Add the `-TimeOut` parameter to `Test-Connection`.</span></span> <span data-ttu-id="805fb-385">(#2492)</span><span class="sxs-lookup"><span data-stu-id="805fb-385">(#2492)</span></span>
- <span data-ttu-id="805fb-386">`Get-AuthenticodeSignature` cmdlet은 이제 파일 서명 타임스탬프를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-386">`Get-AuthenticodeSignature` cmdlets can now get file signature timestamp.</span></span> <span data-ttu-id="805fb-387">(#4061)</span><span class="sxs-lookup"><span data-stu-id="805fb-387">(#4061)</span></span>
- <span data-ttu-id="805fb-388">`Get-Help`에서 지원되지 않는 `-ShowWindow` 스위치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-388">Remove unsupported `-ShowWindow` switch from `Get-Help`.</span></span> <span data-ttu-id="805fb-389">(#4903)</span><span class="sxs-lookup"><span data-stu-id="805fb-389">(#4903)</span></span>
- <span data-ttu-id="805fb-390">반환된 배열 요소에 구분 기호를 포함하지 않도록 `Get-Content -Delimiter`를 수정합니다. (#3706) (@mklement0에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-390">Fix `Get-Content -Delimiter` to not include the delimiter in the array elements returned (#3706) (Thanks @mklement0)</span></span>
- <span data-ttu-id="805fb-391">`Meta`, `Charset`, 및 `Transitional` 매개 변수를 `ConvertTo-HTML`에 추가합니다. (#4184) (@ergo3114에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-391">Add `Meta`, `Charset`, and `Transitional` parameters to `ConvertTo-HTML` (#4184) (Thanks @ergo3114)</span></span>
- <span data-ttu-id="805fb-392">`WindowsUBR` 및 `WindowsVersion` 속성을 `Get-ComputerInfo` 결과에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-392">Add `WindowsUBR` and `WindowsVersion` properties to `Get-ComputerInfo` result</span></span>
- <span data-ttu-id="805fb-393">`-Group` 매개 변수를 `Get-Verb`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-393">Add `-Group` parameter to `Get-Verb`</span></span>
- <span data-ttu-id="805fb-394">`ShouldProcess` 지원을 `New-FileCatalog` 및 `Test-FileCatalog`에 추가합니다(`-WhatIf` 및 `-Confirm` 수정).</span><span class="sxs-lookup"><span data-stu-id="805fb-394">Add `ShouldProcess` support to `New-FileCatalog` and `Test-FileCatalog` (fixes `-WhatIf` and `-Confirm`).</span></span> <span data-ttu-id="805fb-395">(#3074) (@iSazonov에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-395">(#3074) (Thanks to @iSazonov!)</span></span>
- <span data-ttu-id="805fb-396">`-WhatIf` 스위치를 `Start-Process` cmdlet에 추가합니다. (#4735) (@sarithsutha에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-396">Add `-WhatIf` switch to `Start-Process` cmdlet (#4735) (Thanks @sarithsutha)</span></span>
- <span data-ttu-id="805fb-397">`ValidateNotNullOrEmpty` 너무 많은 기존 매개 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-397">Add `ValidateNotNullOrEmpty` too many existing parameters.</span></span>

## <a name="tab-completion"></a><span data-ttu-id="805fb-398">탭 완성</span><span class="sxs-lookup"><span data-stu-id="805fb-398">Tab completion</span></span>

- <span data-ttu-id="805fb-399">런타임 변수 값을 기반으로 탭 완성의 형식 유추를 향상시켰습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-399">Enhanced the type inference in tab completion based on runtime variable values.</span></span> <span data-ttu-id="805fb-400">(#2744) (@powercode에게 감사드립니다!) 이렇게 하면 다음과 같은 상황에서 탭 완성이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-400">(#2744) (Thanks to @powercode!) This enables tab completion in situations like:</span></span>

  ```powershell
  $p = Get-Process
  $p | Foreach-Object Prio<tab>
  ```

- <span data-ttu-id="805fb-401">`Select-Object`의 `-Property`에 대해 해시 테이블 탭 완성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-401">Add Hashtable tab completion for `-Property` of `Select-Object`.</span></span> <span data-ttu-id="805fb-402">(#3625) (@powercode에게 감사드립니다.)</span><span class="sxs-lookup"><span data-stu-id="805fb-402">(#3625) (Thanks to @powercode)</span></span>
- <span data-ttu-id="805fb-403">`-ExcludeProperty`와 `Select-Object`의 `-ExpandProperty`에 인수 자동 완성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-403">Enable argument auto-completion for `-ExcludeProperty` and `-ExpandProperty` of `Select-Object`.</span></span> <span data-ttu-id="805fb-404">(#3443) (@iSazonov에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-404">(#3443) (Thanks to @iSazonov!)</span></span>
- <span data-ttu-id="805fb-405">`native.exe --<tab>`를 네이티브 완성자로 호출하도록 탭 완성의 버그를 수정했습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-405">Fix a bug in tab completion to make `native.exe --<tab>` call into native completer.</span></span> <span data-ttu-id="805fb-406">(#3633) (@powercode에게 감사드립니다!)</span><span class="sxs-lookup"><span data-stu-id="805fb-406">(#3633) (Thanks to @powercode!)</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="805fb-407">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="805fb-407">Breaking changes</span></span>

<span data-ttu-id="805fb-408">PowerShell Core 6.0은 많은 주요 내용이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-408">We've introduced a number of breaking changes in PowerShell Core 6.0.</span></span>
<span data-ttu-id="805fb-409">자세한 내용은 [PowerShell Core 6.0의 주요 변경 내용][breaking-changes]을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="805fb-409">To read more about them in detail, see [Breaking Changes in PowerShell Core 6.0][breaking-changes].</span></span>

## <a name="debugging"></a><span data-ttu-id="805fb-410">디버깅</span><span class="sxs-lookup"><span data-stu-id="805fb-410">Debugging</span></span>

- <span data-ttu-id="805fb-411">`Invoke-Command -ComputerName`에 대한 원격 스텝인 디버깅을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-411">Support for remote step-in debugging for `Invoke-Command -ComputerName`.</span></span> <span data-ttu-id="805fb-412">(#3015)</span><span class="sxs-lookup"><span data-stu-id="805fb-412">(#3015)</span></span>
- <span data-ttu-id="805fb-413">PowerShell Core에서 바인더 디버그 로깅 사용</span><span class="sxs-lookup"><span data-stu-id="805fb-413">Enable binder debug logging in PowerShell Core</span></span>

## <a name="filesystem-updates"></a><span data-ttu-id="805fb-414">파일 시스템 업데이트</span><span class="sxs-lookup"><span data-stu-id="805fb-414">Filesystem updates</span></span>

- <span data-ttu-id="805fb-415">UNC 경로의 파일 시스템 공급자의 사용을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-415">Enable usage of the Filesystem provider from a UNC path.</span></span> <span data-ttu-id="805fb-416">($4998)</span><span class="sxs-lookup"><span data-stu-id="805fb-416">($4998)</span></span>
- <span data-ttu-id="805fb-417">`Split-Path`가 이제 UNC 루트와 함께 작동</span><span class="sxs-lookup"><span data-stu-id="805fb-417">`Split-Path` now works with UNC roots</span></span>
- <span data-ttu-id="805fb-418">인수가 없는 `cd`가 `cd ~`처럼 동작</span><span class="sxs-lookup"><span data-stu-id="805fb-418">`cd` with no arguments now behaves as `cd ~`</span></span>
- <span data-ttu-id="805fb-419">PowerShell Core를 수정하여 260자 보다 더 긴 있는 경로를 사용할 수 있게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-419">Fixed PowerShell Core to allow use of paths that are more than 260 characters long.</span></span> <span data-ttu-id="805fb-420">(#3960)</span><span class="sxs-lookup"><span data-stu-id="805fb-420">(#3960)</span></span>

## <a name="bug-fixes-and-performance-improvements"></a><span data-ttu-id="805fb-421">버그 수정 및 성능 향상</span><span class="sxs-lookup"><span data-stu-id="805fb-421">Bug fixes and performance improvements</span></span>

<span data-ttu-id="805fb-422">시작 시간, 다양한 기본 제공 cmdlet 및 네이티브 이진 파일과의 상호 작용 등 PowerShell 전체 성능이 *대폭* 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-422">We've made *many* improvements to performance across PowerShell, including in startup time, various built-in cmdlets, and interaction with native binaries.</span></span>

<span data-ttu-id="805fb-423">또한 PowerShell Core 내의 여러 가지 버그를 수정했습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-423">We've also fixed a number of bugs within PowerShell Core.</span></span>
<span data-ttu-id="805fb-424">수정 사항 및 변경 사항 전체 목록은 GitHub의 [changelog][]를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="805fb-424">For a complete list of fixes and changes, check out our [changelog][] on GitHub.</span></span>

## <a name="telemetry"></a><span data-ttu-id="805fb-425">원격 분석</span><span class="sxs-lookup"><span data-stu-id="805fb-425">Telemetry</span></span>

- <span data-ttu-id="805fb-426">PowerShell Core 6.0은 다음과 같은 두 값을 보고하기 위해 콘솔 호스트에 원격 분석 기능을 추가했습니다. (#3620)</span><span class="sxs-lookup"><span data-stu-id="805fb-426">PowerShell Core 6.0 added telemetry to the console host to report two values (#3620):</span></span>
  - <span data-ttu-id="805fb-427">OS 플랫폼(`$PSVersionTable.OSDescription`)</span><span class="sxs-lookup"><span data-stu-id="805fb-427">the OS platform (`$PSVersionTable.OSDescription`)</span></span>
  - <span data-ttu-id="805fb-428">PowerShell의 정확한 버전(`$PSVersionTable.GitCommitId`)</span><span class="sxs-lookup"><span data-stu-id="805fb-428">the exact version of PowerShell (`$PSVersionTable.GitCommitId`)</span></span>

<span data-ttu-id="805fb-429">이 원격 분석을 옵트아웃하려면 간단히 `$PSHome\DELETE_ME_TO_DISABLE_CONSOLEHOST_TELEMETRY`를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-429">If you want to opt-out of this telemetry, simply delete `$PSHome\DELETE_ME_TO_DISABLE_CONSOLEHOST_TELEMETRY`.</span></span>
<span data-ttu-id="805fb-430">이 파일을 삭제하면 PowerShell의 첫 실행 전이라도 모든 원격 분석을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-430">Deleting this file bypasses all telemetry even before the first run of PowerShell.</span></span>
<span data-ttu-id="805fb-431">또한 이 원격 분석 데이터와 [커뮤니티 대시보드][community-dashboard]의 원격 분석에서 얻은 정보를 공개할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-431">We also plan on exposing this telemetry data and the insights we glean from the telemetry in the [community dashboard][community-dashboard].</span></span>
<span data-ttu-id="805fb-432">[블로그 게시물][telemetry-blog]에서 이 데이터를 사용하는 방법에 대해 자세히 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805fb-432">You can find out more about how we use this data in this [blog post][telemetry-blog].</span></span>

[github]: https://github.com/PowerShell/PowerShell
[.NET Core 2.0]: https://docs.microsoft.com/en-us/dotnet/core/
[.NET Standard]: https://docs.microsoft.com/en-us/dotnet/standard/net-standard
[os_log]: https://developer.apple.com/documentation/os/logging
[Syslog]: https://en.wikipedia.org/wiki/Syslog
[ssh-remoting]: ../core-powershell/SSH-Remoting-in-PowerShell-Core.md
[breaking-changes]: https://github.com/PowerShell/PowerShell/tree/master/docs/BREAKINGCHANGES.md
[changelog]: https://github.com/PowerShell/PowerShell/tree/master/CHANGELOG.md
[community-dashboard]: https://aka.ms/PSGitHubBI
[telemetry-blog]: https://blogs.msdn.microsoft.com/powershell/2017/01/31/powershell-open-source-community-dashboard/
[.NET Standard]: https://docs.microsoft.com/dotnet/standard/net-standard
[.NET Blog]: https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard
[YouTube]: https://www.youtube.com/watch?v=YI4MurjfMn8&list=PLRAdsfhKI4OWx321A_pr-7HhRNk7wOLLY
[FAQ]: https://github.com/dotnet/standard/blob/master/docs/faq.md
[CDXML]: https://msdn.microsoft.com/en-us/library/jj542525(v=vs.85).aspx
[docker-hub]: https://hub.docker.com/r/microsoft/powershell/
[docker]: https://github.com/PowerShell/PowerShell/tree/master/docker
[windowspsmodulepath]: https://www.powershellgallery.com/packages/WindowsPSModulePath/
[semi-annual]: https://docs.microsoft.com/windows-server/get-started/semi-annual-channel-overview