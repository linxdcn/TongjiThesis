# Tongji Thesis - 同济大学论文模板
## 版本说明
- 该模板由[linxdcn](https://github.com/linxdcn/TongjiThesis)修改维护。
- 模板最初由Tongji LUG创作，2014年的[RC2](https://sourceforge.net/projects/tongjithesis/)版本之后似乎已停止维护。此版本融合了wildwolf、[svandex](https://github.com/svandex/masthesis)、[zhao-chen](https://github.com/zhao-chen/TongjiThesis)的部分修改。

## 使用说明

### 参考文献

	@Book{companion,
		author    = "Michel Goosens and Frank Mittelbach and Alexander Samarin",
		title     = "The {\LaTeX} Companion",
		publisher = "Addison-Wesley Publishing Company",
		address   = "Reading, MA",
		PAGES = "112--125",
		year      = 1994,
	}

	@PhdThesis{shaheshang,
	  	author  = {沙和尚 and 孙悟空 and 唐僧},
	  	title   = {论流沙河的综合治理},
		school  = {清华大学},
		year    = {2005},
		address = {北京},
		lang    = {zh},
		pinyin  = {shaheshang}
	}

效果一

	英文引用\cite{companion}，中文引用\cite{shaheshang}

英文引用 (Goosens et al. 1994)，中文引用 (沙和尚 等 2005)

效果二

	`英文引用(Goosens等, \citeyear{companion})，中文引用(沙和尚等, \citeyear{shaheshang})`

英文引用 (Goosens 等, 1994)，中文引用 (沙和尚等, 2005)

效果三

	`Goosens等\citeyearpar{companion}，沙和尚等\citeyearpar{shaheshang}`

Goosens 等 (1994)，沙和尚等 (2005)

注意

* 中文文献应该添加`lang`和`pinyin`域，`lang`用于分离中英文文献，默认为英文；`pinyin`用于中文文献排序。

### 添加公式

公式编辑可使用mathtype，将编辑好的公式直接拷贝到latex的文件

效果一

	\begin{equation}
		E = m c^2
	\end{equation}

### 添加图

效果一

	\begin{figure}[htb!]
		\centering
		\includegraphics[width=0.75\textwidth]{tongji-whole-logo.eps}
		\caption{校徽和校名}
		\label{fig:logo}
	\end{figure}	

![](/example/figure1.jpg)

效果二

	\begin{figure}[!h] 
		\centering 
		\begin{tabular}{cc} 
			\includegraphics[width=6cm]{tongji-whole-logo.eps} & \includegraphics[width=6cm]{tongji-whole-logo.eps}\\ 
			(a)图1 & (b)图2
		\end{tabular} 
		\caption{同济大学} 
		\label{fig:subimage} 
	\end{figure}

![](/example/figure2.jpg)

效果三

	\begin{figure}[!h] 
		\noindent 
		\begin{minipage}[t]{.48\linewidth} 
			\centering 
				\includegraphics[width=6cm]{tongji-whole-logo.eps} 
			\caption{图1} 
			\label{fig:quadratic} 
		\end{minipage} 
		\begin{minipage}[t]{.48\linewidth} 
			\centering 
			\includegraphics[width=6cm]{tongji-whole-logo.eps} 
				\caption{图2} 
			\label{fig:triorder} 
		\end{minipage} 
	\end{figure}

![](/example/figure3.jpg)

### 添加表

表格编辑可使用[excel2latex](https://ctan.org/tex-archive/support/excel2latex/)。

较好的效果

	\begin{table}[!htb]
	  	\centering
	  	\caption{Add caption}
	  	\label{tab:events}
	    \begin{tabular}{?c"c?}
		    \thickhline
		    a     & b \bigstrut\\
		    \thinhline
			第一列   & 第二列 \bigstrut\\
		    \thinhline
		    第一列   & 第二列 \bigstrut\\
		    \thinhline
		    第一列   & 第二列 \bigstrut\\
		    \thickhline
	    \end{tabular}%
	  \label{tab:addlabel}
	\end{table}

![](/example/table1.jpg)

## 字体说明

- 模板使用了TeXlive默认的Fandol中文字体（Bold支持较好），没有Fandol字体可从[这里](https://www.ctan.org/tex-archive/fonts/fandol)下载
- 如需使用Windows或者Mac自带的字体，可将cls文件对应的代码取消注释
- 可如需使用Adobe或其他字体，可自行在cls文件中修改。

## 注意
- 未完全测试，尽量使用UTF-8文件编码，xelatex编译，以免出现意外问题。
- 已知问题：
    + xelatex编译速度比pdflatex慢，需要耐心等待。
    + 用TeXStudio可能编译时会跳出对话框，提示“日志文件很大，确认载入？”，选择“是”即可照样继续
    + 推荐使用Sublime Text + LaTeXTools，常用快捷键：由Latex查找PDF：ctrl+L(松开接)J；清理临时文件：ctrl+L(松开接)Backspace
- 若有其他问题，欢迎指正或留言讨论。

## Todo

- 封面、原创性说明、版权授权前面几页格式与论文规范不一致
- 暂未包含书脊
