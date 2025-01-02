1. 对于未定义的特殊函数，请使用 `\mathrm{}` 环境，例如微分算子 $\mathrm{d}$，Tree 函数 $\mathrm{Tree()}$
2. 对于已定义的函数，请直接使用，例如最大公约数 $\gcd$，自然对数 $\ln$
4. 对于化学方程式，请使用 `\ce{}` 环境，例如 $\ce{CH4(g) + 2O2(g) ->[\pu{600 \degree C}][催化剂] CO2(g) + 2H2O(g)}$
5. 对于单位，请使用 `\pu{}` 环境，例如 $\pu{600 \degree C}$, $\pu{1 mol/L}$, $\pu{1.14514e3 N*s}$
6. 对于分数，酌情考虑使用 `\dfrac` 替代 `\frac`，因为 $\dfrac{114514^2}{1919880^2}$ 和 $\frac{114514^2}{1919880^2}$ 它真的不一样
7. 对于箭头，请使用 $\rightarrow$，$\leftarrow$，而不是 $→$ ，$←$（在 $\LaTeX$ 中塞一个真的很突兀）（所有横向箭头均有快捷键，在设置 - 第三方插件 -Quick Latex-Custom Shorthand Parameter 中可以看到）
8. 如何使用快捷键？以 `\mathrm{}` 为例： `Shift` + `4`；`r`；`m`；`Space`；其他快捷键同理