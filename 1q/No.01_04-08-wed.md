# 第１回

## 1.1 OS とは

- ハードウェアを直接操作するアプリケーションは難しい。
	- ハードウェアの操作方法
	- ハードウェアの共有方法
$$
\Downarrow
\hspace{12cm}
$$
	ハードウェアを使いやすくする為に間を取り持つのが、<span style="color: red;">オペレーティングシステム</span>

### 三大機能

#### 1. 資源管理者の機能
- ハードウェア資源 = CPU, メモリ, ...
- ソフトウェア資源 = プログラム, データ

#### 2. 制御プログラムの機能
- ハードウェアへのアクセス制御

#### 3. ハードウェアの抽象化機能
- ハードウェアごとの違いを吸収して、プログラム開発者がハードウェアごとの特性を意識せずに開発が可能。

- <span style="color: red;">API (Application Program Interface)</span>
	- OSにおけるAPI: OSがアプリケーションに公開している機能のこと。
	- ハードウェアとアプリケーションの間にあるインターフェースの差を吸収。
	- アプリケーションが直接ハードウェアにアクセスしない。
		= アプリケーションが暴走しても、システム全体に影響が及ばない。

### OSの分類
$$
\begin{cases}
	\color{red}\text{シングルタスクOS}\color{black}: \text{一度に1つのプログラムしか実行できないOS.} \\
	\color{red}\text{マルチタスクOS}\color{black}: \text{複数のプログラムを同時に実行できるOS.}
\end{cases}
\hspace{8cm}
$$
$$
\begin{cases}
	\textcolor{red}{シングルユーザOS}: \text{1度に1人のユーザしか使用できないことを前提としたOS.} \\
	\textcolor{red}{マルチユーザOS}: \text{複数のユーザが同時にログインして利用できることを前提としたOS.} \\
\end{cases}
\hspace{2cm}
$$
> シングルユーザOSは、<span style="color: blue">複数人が同時に使えない</span>

|             | シングルタスク |         マルチタスク          |
| :---------: | :-----: | :---------------------: |
| **シングルユーザ** | MS-DOS  |    Windows<br>macOS     |
| **マルチユーザ**  |         | Linux<br>Windows Server |

#### マルチタスク・マルチユーザを実現する為の技術
$$
\begin{gathered}
\boxed{
	\begin{aligned}
		&\bullet \textcolor{red}{\text{時分割多重}}: \text{時間を区切って、ハードウェア資源を共有する (CPUなど) 。} \\
		&\bullet \textcolor{red}{\text{空間分割多重}}: \text{記憶領域を複数のプログラムに分けて割り当てる (主記憶、補助記憶) 。}
	\end{aligned}
} \\
\Downarrow
\end{gathered}
$$
<div style="text-align: center;">
	<span style="color: red;">仮想化</span><br>	
	ハードウェア資源を時分割と空間分割によって多重化し、<br>
	各ユーザが自分専用の資源を持っているかのように見せる技術。
</div>

- <span style="color: red;">分割処理 (Distributed processing)</span>
	- 複数のコンピュータをネットワークで結合し、互いに通信しながら利用する方式
	- <span style="color: blue">故障の原因特定が難しいが、スケーラビリティが高い。</span>
	
- <span style="color: red;">集中処理 (Centralized processing)</span>
	- 1台のコンピュータで処理を行う方式。
	- <span style="color: blue">管理・セキュリティが楽。全体が中央コンピュータに依存し、もし中央コンピュータで障害が起これば全体に広がる。</span>