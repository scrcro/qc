# Reflection Operator Derivation

While learning about Grover's algorithm, I came across the "reflection" operator. It was simply stated as $`2\ket{s}\bra{s} -  \mathbb{1}`$.
But there was no derivation shown. Perhaps this is a simple one for Physics major but for me this was a bit unsatisfying unless I could derive it. Internet search including ChatGPT and Copilot was futile. Google Gemini did a bit better but far from satisfying. Hence the derivation and this may help others.

**Projection Operator:**
Projection of a ket $`\ket{p}`$ on to another ket $`\ket{s}`$ is $`\ket{s}\braket{s|p}`$. This simplifies to $`\alpha\ket{s}`$, where $`\alpha = \braket{s|p}`$. Clearly, this is the component of $`\ket{p}`$ on  $`\ket{s}`$. 

**Reflection:**
Reflection of a ket $`\ket{p}`$ around another ket $`\ket{s}`$ can be achieved by keeping the component of $`\ket{p}`$ along $`\ket{s}`$ as is, and negating the component of $`\ket{p}`$ along perpendicular to $`\ket{s}`$ say ket $`\ket{r}`$. Hence, $`\ket{p} = \alpha\ket{s} + \beta\ket{r}`$. Therefore:  
```math
\begin{align*}
R\ket{p} = \alpha\ket{s} - \beta\ket{r}\\
R\ket{p} = \ket{s}\braket{s|p} - \ket{r}\braket{r|p}\\
\implies R = \ket{s}\bra{s} - \ket{r}\bra{r}\\
\implies R = \ket{s}\bra{s} + \ket{s}\bra{s} - \ket{r}\bra{r} - \ket{s}\bra{s}\\
\implies R = 2\ket{s}\bra{s} - (\ket{r}\bra{r} + \ket{s}\bra{s})\\   
\implies R = 2\ket{s}\bra{s} - \mathbb{1} \ \because \ket{r}\bra{r} + \ket{s}\bra{s} =  \mathbb{1}
\end{align*}
```
