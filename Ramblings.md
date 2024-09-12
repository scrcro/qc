# Reflection Operator Derivation

While learning about Grover's algorithm, I came across the "reflection" operator. It was simply stated as $`2\ket{s}\bra{s} -  \mathbb{1}`$.
But there was no derivation shown. Perhaps this is a simple one for Physics major but for me this was a bit unsatisfying unless I could derive it. Internet search including ChatGPT and Copilot was futile. Google Gemini did a bit better but far from satisfying. Hence the derivation and this may help others.

**Projection Operator:**
Projection of a ket $`\ket{p}`$ on to another ket $`\ket{s}`$ is $`\ket{s}\braket{s|p}`$. This simplifies to $`\alpha\ket{s}`$, where $`\alpha = \braket{s|p}`$. Clearly, this is the component of $`\ket{p}`$ along  $`\ket{s}`$. 

**Reflection:**
Reflection of a ket $`\ket{p}`$ around another ket $`\ket{s}`$ can be achieved by keeping the component of $`\ket{p}`$ along $`\ket{s}`$ as is, and negating the component of $`\ket{p}`$, say ket $`\ket{r}`$, along orthogonal to $`\ket{s}`$. Hence if, $`\ket{p} = \alpha\ket{s} + \beta\ket{r}`$. Then:  
```math
\begin{align*}
R\ket{p} &= \alpha\ket{s} - \beta\ket{r}\\
R\ket{p} &= \ket{s}\braket{s|p} - \ket{r}\braket{r|p}\\
\implies R &= \ket{s}\bra{s} - \ket{r}\bra{r}\\
\implies R &= \ket{s}\bra{s} + \ket{s}\bra{s} - \ket{r}\bra{r} - \ket{s}\bra{s}\\
\implies R &= 2\ket{s}\bra{s} - (\ket{r}\bra{r} + \ket{s}\bra{s})\\   
\implies R &= 2\ket{s}\bra{s} - \mathbb{1} \   &\because \ket{r}\bra{r} + \ket{s}\bra{s} =  \mathbb{1}
\end{align*}
```

# Grover's Algorithm : Oracle Formation

While learning about Grover's alogrithm, I came across the "oracle". In most implementation and examples, the "oracle" seem to already solve the search problem. How? We say the "oracle" is able to "mark" the desired "state(s)". Weill if they are able to do that then why search using Grover's algorithm? 
Here is what I figured eventually, the "oracle" is indeed able to mark but we need to query the "oracle" with the inputs. Where Grover's algorithm wins is the number of query one would have to make to the **"oracle"** vs a classical "oracle" that performs the same function. Many hours spent on internet search kind of points to this and this makes sense too. Further, the oracle really does not know the answer, but it can detect certain properties of the answer. Generally must be a boolean condition which evaluates to 1 for the correct answers and 0 for others. E.g. $`SHA256(x) = y `$ where $`x`$ is the input and $`y`$ is the SHA256 string.
