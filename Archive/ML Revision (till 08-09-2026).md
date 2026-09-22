# ML Revision

## Topics Done:

### Lecture 1
- **Definition of ML:** a field of study that gives computers the ability to learn from data without being explicitly programmed.
- **Workflow:** data collection → cleaning / preprocessing → train-test split → training → evaluation → deployment.
- **Types of ML (with examples):**
    - Supervised — labelled data (e.g., price prediction, spam detection)
    - Unsupervised — unlabelled data (e.g., customer segmentation, clustering)
    - Reinforcement — learns from rewards / punishments (e.g., game playing, robotics)

### Lecture 2
- Definition of linear regression
- Types of regression
- Formula of linear regression ($y=mx+c$ or $y=a_{0}+a_{1}*x$)
	- where $y$ is value to predict
	- $x$ is the value we know
	- $m$ is the slope
- $y=a_{0}+a_{1}*x+e$
    - $e$ = error / residual term (difference between predicted and actual $y$)
- $a_{1}= \frac{\sum(x_{i}-\bar{x})(y_{i}-\bar{y})}{\sum(x_{i}-\bar{x})^{2}}$ (least-squares slope)
    - $a_1$ = slope, $a_0$ = intercept

- <svg version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 480.47674560546875 342.3367462158203" width="480.47674560546875" height="342.3367462158203"><!-- svg-source:excalidraw --><metadata></metadata><defs><style class="style-fonts">
      @font-face { font-family: Excalifont; src: url(data:font/woff2;base64,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); }</style></defs><rect x="0" y="0" width="480.47674560546875" height="342.3367462158203" fill="#ffffff"></rect><g stroke-linecap="round"><g transform="translate(10 10) rotate(0 0.3714599609375 160.79691314697266)"><path d="M0 0 C0.12 53.6, 0.62 267.99, 0.74 321.59 M0 0 C0.12 53.6, 0.62 267.99, 0.74 321.59" stroke="#1971c2" stroke-width="2" fill="none"></path></g></g><mask></mask><g stroke-linecap="round"><g transform="translate(10.742919921875 332.3367462158203) rotate(0 224.66818237304688 -1.11431884765625)"><path d="M0 0 C74.89 -0.37, 374.45 -1.86, 449.34 -2.23 M0 0 C74.89 -0.37, 374.45 -1.86, 449.34 -2.23" stroke="#1971c2" stroke-width="2" fill="none"></path></g></g><mask></mask><g stroke-linecap="round"><g transform="translate(11.4827880859375 166.70948791503906) rotate(0 229.49697875976562 -30.410087689937484)"><path d="M0 0 C7.8 -0.25, 34.29 6.32, 46.79 -1.48 C59.29 -9.28, 65.48 -50.01, 75.01 -46.79 C84.55 -43.57, 89.74 28.97, 103.98 17.83 C118.21 6.69, 143.59 -121.56, 160.43 -113.63 C177.26 -105.71, 187.04 44.56, 204.99 65.36 C222.94 86.16, 254.01 14.85, 268.12 11.14 C282.23 7.43, 277.4 51.99, 289.66 43.08 C301.91 34.17, 325.06 -41.1, 341.65 -42.33 C358.23 -43.57, 369.62 50.26, 389.18 35.65 C408.74 21.04, 447.36 -102.37, 458.99 -129.97 M0 0 C7.8 -0.25, 34.29 6.32, 46.79 -1.48 C59.29 -9.28, 65.48 -50.01, 75.01 -46.79 C84.55 -43.57, 89.74 28.97, 103.98 17.83 C118.21 6.69, 143.59 -121.56, 160.43 -113.63 C177.26 -105.71, 187.04 44.56, 204.99 65.36 C222.94 86.16, 254.01 14.85, 268.12 11.14 C282.23 7.43, 277.4 51.99, 289.66 43.08 C301.91 34.17, 325.06 -41.1, 341.65 -42.33 C358.23 -43.57, 369.62 50.26, 389.18 35.65 C408.74 21.04, 447.36 -102.37, 458.99 -129.97" stroke="#e03131" stroke-width="2" fill="none"></path></g></g><mask></mask><g stroke-linecap="round"><g transform="translate(96.16260963566971 221.08766174316406) rotate(0 6.679391593297957 -17.902862548828125)"><path d="M0 0 C2.23 -5.97, 11.13 -29.84, 13.36 -35.81 M0 0 C2.23 -5.97, 11.13 -29.84, 13.36 -35.81" stroke="#2f9e44" stroke-width="2" fill="none"></path></g><g transform="translate(96.16260963566971 221.08766174316406) rotate(0 6.679391593297957 -17.902862548828125)"><path d="M13.21 -16.7 C13.24 -20.76, 13.27 -24.82, 13.36 -35.81 M13.21 -16.7 C13.26 -23.93, 13.32 -31.17, 13.36 -35.81" stroke="#2f9e44" stroke-width="2" fill="none"></path></g><g transform="translate(96.16260963566971 221.08766174316406) rotate(0 6.679391593297957 -17.902862548828125)"><path d="M0.96 -21.27 C3.59 -24.36, 6.23 -27.44, 13.36 -35.81 M0.96 -21.27 C5.65 -26.77, 10.35 -32.28, 13.36 -35.81" stroke="#2f9e44" stroke-width="2" fill="none"></path></g></g><mask></mask><g stroke-linecap="round"><g transform="translate(203.34254838785694 279.0216522216797) rotate(0 9.163198462321528 -19.390121459960938)"><path d="M0 0 C3.05 -6.46, 15.27 -32.32, 18.33 -38.78 M0 0 C3.05 -6.46, 15.27 -32.32, 18.33 -38.78" stroke="#2f9e44" stroke-width="2" fill="none"></path></g><g transform="translate(203.34254838785694 279.0216522216797) rotate(0 9.163198462321528 -19.390121459960938)"><path d="M16.35 -17.43 C16.88 -23.13, 17.41 -28.84, 18.33 -38.78 M16.35 -17.43 C16.92 -23.57, 17.49 -29.72, 18.33 -38.78" stroke="#2f9e44" stroke-width="2" fill="none"></path></g><g transform="translate(203.34254838785694 279.0216522216797) rotate(0 9.163198462321528 -19.390121459960938)"><path d="M3.08 -23.69 C7.16 -27.73, 11.23 -31.76, 18.33 -38.78 M3.08 -23.69 C7.47 -28.04, 11.86 -32.38, 18.33 -38.78" stroke="#2f9e44" stroke-width="2" fill="none"></path></g></g><mask></mask><g transform="translate(39.69205856323242 227.08766174316406) rotate(0 54.22116261546498 11.758590698242188)"><text x="0" y="16.574909448242185" font-family="Excalifont, Xiaolai, sans-serif, Segoe UI Emoji" font-size="18.813745117187498px" fill="#1e1e1e" text-anchor="start" style="white-space: pre;" direction="ltr" dominant-baseline="alphabetic">Local minima</text></g><g transform="translate(137.7246208190918 285.0216522216797) rotate(0 62.76995086669922 12.5)"><text x="0" y="17.619999999999997" font-family="Excalifont, Xiaolai, sans-serif, Segoe UI Emoji" font-size="20px" fill="#1e1e1e" text-anchor="start" style="white-space: pre;" direction="ltr" dominant-baseline="alphabetic">Global minima</text></g></svg>
- Normal Equation (matrix method)
	- $a=((X^TX)^{-1}X^T)Y$
- Computational Complexity
	- Matrix inversion complexity ($O(n^3)$)
	- where $n$ is number of features (Independent Variables)

### Lecture 3
- Convergence: Gradually reaching a stable or a final value
- Local minima: lowest point within a neighbourhood; Global minima: lowest point over the entire surface
- Local maxima: highest point within a neighbourhood; Global maxima: highest point over the entire surface

- Working of gradient descent
- $J(w,b)=\frac{1}{2m}\sum(y_{pred}-y)^2$
- $w=w-\alpha\frac{\partial{J}}{\partial{w}}$
- Large and Good Learning Rate
    - $\alpha$ too large → overshoots the minimum, may diverge
    - $\alpha$ too small → converges very slowly
    - A good rate is large enough to converge quickly, small enough not to overshoot
- $y_{pred}=wx+b$
- $J$ is the cost function
- $\frac{\partial{J}}{\partial{w}}=\frac{1}{m}\sum(y_{p}-y)$

### Lecture 4
- Variants of Gradient Descent
	- Batch
	- Mini-Batch
	- Stochastic
- Multiple Linear Regression
- $b_{1}=\frac{S_{1y}S_{22}-S_{2y}S_{12}}{S_{11}S_{22}-S_{12}^2}$
- $b_{2}=\frac{S_{2y}S_{11}-S_{1y}S_{12}}{S_{11}S_{22}-S_{12}^2}$
- $b_{0}=\bar{y}-b_{1}\bar{x}_{1}-b_{2}\bar{x}_{2}$ (intercept, computed once the slopes are known) 