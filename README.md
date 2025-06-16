# Gnuplot

$y=sin(x)，tan^{-1}(x)$ のグラフを描く

```gnuplot {cmd=true output="html"}
set terminal svg
set xrange [0:7]
set yrange [-20:15]
set title "関数のプロット"
set xlabel "x"
set ylabel "y"
set grid

f1(x)=2*x**2*sqrt(x)-5*x*x
f2(x)=x/log(x)

plot f1(x) title "f1(x)",f2(x) title "f2(x)"

```

```gnuplot {cmd=true, output="html"}
set terminal svg
set xdata time
set timefmt '%Y/%m/%d'
set xtics format "%m/%d"

set datafile separator","
set title "八王子の気温（過去１年間）"
set xlabel "日付"
set ylabel "温度"
set grid
prot "weather2025.csv" using 1:2 title "最高気温" with lines lcrgb "purple",\
"" using 1:3 title "最高気温（平年）"　with lines lc rab "green",\ using 1:4 title  "最低気温"　with lines lc lab "skyblue",\ ""using 1:5 title "最低気温（平年）"　with lines lc rab "orange"
```

```gnuplot {cmd=true, output="html"}
set terminal svg
unset key

set title "誕生日の月別人数"
set xlavel ""

set ylabel"人"　offset graph 0,0.5 rotate by 0
 set style fill solid 1.0
 set boxwidth 0.6
 set yrange [0:16]
 set gnd

  set xtics("１月" 0,"２月" 1,"３月"2,"４月" 3,"５月" 4,"６月" 5,\ "７月" 6,"８月" 7,"９月" 8,"１０月" 9,"11月" 10,"12月"11)
  
  plot "bm.txt" using 0:2 with boxes lc rgb "skyblue" notitle


```