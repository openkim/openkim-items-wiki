This 4-body potential is a modification of the Stillinger-Weber model for silicon, where a four-body term is added and angle dependence of the 3-body and 4-body terms has been changed. These modifications results in qualitative improvement for silicon. More specifically, good values for the energy of ground states of clusters obtained for a large range of the parameters of the 3-body and 4-body terms. 
Functional form of this potential:

$$
\begin{align*}
 & \phi(1,2,...,N) =\sum_{1 \leq i \leq N} V_{1}(\textbf{r}_i)+\sum_{1 \leq i \leq j \leq N} V_{2}(\textbf{r}_i,\textbf{r}_j)+\sum_{1 \leq i \leq j \leq k \leq N} V_{3}(\textbf{r}_i,\textbf{r}_j,\textbf{r}_k)+\sum_{1 \leq i \leq j \leq k \leq l \leq N} V_{4}(\textbf{r}_i,\textbf{r}_j,\textbf{r}_k,\textbf{r}_l)&
\end{align*}
$$

where

$$ 
\begin{align*}
&V_{1}(\textbf{r}_i)=0
\end{align*}
$$

$$ 
\begin{align*}
&V_{2}(\textbf{r}_i,\textbf{r}_j)=v_{2}(r_{ij})
\end{align*}
$$

$$ 
\begin{align*}
&v_{2}(r_{ij})=\left\{
\begin{aligned}
&A\left(B/r_{ij}^4-1\right)\exp\left[\alpha(r_{ij}-R)^{-1}\right] , r_{ij}<R \\
&0 , otherwise \\
\end{aligned}
\right.
\end{align*}
$$

$$ 
\begin{align*}
&V_{3}(\textbf{r}_i,\textbf{r}_j,\textbf{r}_k)=v_{3}\left(r_{ij},r_{ik},\theta_{jik}\right)+v_{3}\left(r_{jk},r_{ji},\theta_{ijk}\right)+v_{3}\left(r_{ki},r_{kj},\theta_{ikj}\right)
\end{align*}
$$

$$ 
\begin{align*}
&v_{3}\left(r_{ij},r_{ik},\theta_{jik}\right)=v_{3r}\left(r_{ij},r_{ik}\right)\cdot v_{3\theta}\left(\theta_{jik}\right)
\end{align*}
$$

$$ 
\begin{align*}
&v_{3r}\left(r_{ij},r_{ik}\right)=\left\{
\begin{aligned}
&\exp\left[\gamma(r_{ij}-R)^{-1}+\gamma(r_{ik}-R)^{-1}\right] ,  r_{ij}<R \quad   r_{ik}<R\\
&0  ,  otherwise
\end{aligned}
\right.
\end{align*}
$$

$$ 
\begin{align*}
&v_{3\theta}\left(\theta_{jik}\right)=\lambda_{3}\left\{1-\exp\left[-Q\left(\cos\theta_{jik}+1/3\right)^2\right]\right\}
\end{align*}
$$

$$ 
\begin{align*}
&V_{4}(\textbf{r}_i,\textbf{r}_j,\textbf{r}_k,\textbf{r}_l)=v_{4}\left(r_{ij},r_{ik},r_{il},\theta_{jik},\theta_{jil},\theta_{kil}\right)+v_{4}\left(r_{ji},r_{jk},r_{jl},\theta_{ijk},\theta_{ijl},\theta_{kjl}\right)+v_{4}\left(r_{ki},r_{kj},r_{kl},\theta_{ikj},\theta_{ikl},\theta_{jkl}\right)+v_{4}\left(r_{li},r_{lj},r_{lk},\theta_{ilj},\theta_{ilj},\theta_{jlk}\right)
\end{align*}
$$

$$ 
\begin{align*}
&v_{4}\left(r_{ij},r_{ik},r_{il},\theta_{jik},\theta_{jil},\theta_{kil}\right)=v_{4r}\left(r_{ij},r_{ik},r_{il}\right)\cdot v_{4\theta}\left(\theta_{jik},\theta_{jil},\theta_{kil}\right)
\end{align*}
$$

$$ 
\begin{align*}
&v_{4r}\left(r_{ij},r_{ik},r_{il}\right)=\left\{
\begin{aligned}
&\exp\left[\gamma(r_{ij}-R)^{-1}+\gamma(r_{ik}-R)^{-1}+\gamma(r_{il}-R)^{-1}\right] ,  r_{ij}<R \quad r_{ik}<R\quad r_{il}<R\\
&0  ,  otherwise
\end{aligned}
\right.
\end{align*}
$$

$$ 
\begin{align*}
&v_{4\theta}\left(\theta_{jik},\theta_{jil},\theta_{kil}\right)=\lambda_{4}\left\{1-\exp\left[-Q\left(\cos\theta_{jik}+1/3\right)^2-Q\left(\cos\theta_{jil}+1/3\right)^2-Q\left(\cos\theta_{kil}+1/3\right)^2\right]\right\}
\end{align*}
$$

For silicon, the parameters are recommended to be

$$
\begin{align*}
& \alpha=2.0951 \quad \rm \overset{\circ}{A}\\
& R=3.77118\quad \rm \overset{\circ}{A}\\
& B=11.58113\quad \rm \overset{\circ}{A}\\
& A=16.30076\quad \rm eV\\
& Q=5.0\\
&\gamma=2.4\\
&\lambda_3=4.0\\
&\lambda_4=47.0\\
&
\end{align*}
$$

The following figure shows the plot of $$v_{2}(r_{ij})$$:

![](/wimage/MD_514777050453_000/butnowdevil/2BodyPotential){:height="400px"}

The following figure shows the plot of $$v_{3r}\left(r_{ij},r_{ik}\right)$$:

![](/wimage/MD_514777050453_000/butnowdevil/3BodyPotentialPart1){:height="400px"}

The following figure shows the plot of $$v_{3\theta}\left(\theta_{jik}\right)$$:

![](/wimage/MD_514777050453_000/butnowdevil/3BodyPotentialPart2){:height="400px"}

The following figure shows the plot of $$v_{4r}\left(r_{ij},r_{ik},r_{il}\right)$$:

![](/wimage/MD_514777050453_000/butnowdevil/4BodyPotentialPart1){:height="400px"}

The following figure shows the plot of $$vv_{4\theta}\left(\theta_{jik},\theta_{jil},\theta_{kil}\right)$$:

![](/wimage/MD_514777050453_000/butnowdevil/4BodyPotentialPart2){:height="400px"}

Reference:

A. D. Mistriotis, N. Flytzanis, and S. C. Farantos, "Potential model for silicon clusters", Phys. Rev. B, vol. 39, 1212-1218, 1989
