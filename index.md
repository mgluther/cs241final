<head>
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>

	<title>Data for Data</title>
	
	<style type="text/css" media="screen">
	
		body {
			line-height: 140%;
			width: 800px;
			counter-reset: h1counter;
			margin: auto;
		}
		code {font-size: 120%;}
		
		
		pre code {
			background-color: #00bfb2;
			color: #000000;
			
			display: block;
			padding: 20px;
		}
		
		.centered {
			position: fixed;
			top: 50%;
			left: 50%;
			transform: translate(-50%, -50%);
		}
    		h1 {
        		counter-reset: h2counter;
    			}
    		h2 {
        		counter-reset: h3counter;
   			 }
    		h2:before {
        		content: counter(h2counter) ".\0000a0\0000a0";
        		counter-increment: h2counter;
   			 }
    		h3:before {
        		content: counter(h2counter) "." counter(h3counter) ".\0000a0\0000a0";
        		counter-increment: h3counter;
			}
		
	</style>
	
</head>
	


<body bgcolor="000000" text="00bfb2">
	<h1> D&D Spell Schools Analysis </h1>
	<p> Counts and compares the number of each spell in D&D 5th edition </p>
	<center>
	<img src="spells.png" height=640px>
	</center>
	<h2>The codes that generats the visualization</h2>
	<pre><code>
        df = pd.read_csv('dnd-spells.csv', index_col=0)




        plt.rcParams['figure.figsize'] = [10, 10]
        plt.rcParams['figure.dpi'] = 200
        plt.style.use("dark_background")
        sns.set_style('whitegrid')
        p = sns.countplot(x='school', data=df, palette="mako")
        for tick_label in p.get_yticklabels():
        tick_label.set_color("white")
        for tick_label in p.get_xticklabels():
        tick_label.set_color("white")
        p.get_figure().savefig("spells.png",bbox_inches='tight',transparent=False)

	</code></pre>
	
</body>
