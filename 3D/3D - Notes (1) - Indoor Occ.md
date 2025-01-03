> [!PDF|red] [[EmbodiedOcc.pdf#page=1&selection=59,11,62,11&color=yellow|EmbodiedOcc, p.1]]
> > In this paper, we formulate an embodied 3D occupancy prediction task to target this practical scenario and propose a Gaussian-based EmbodiedOcc framework to accomplish it

[[EmbodiedOcc.pdf]]
- 具身3D Occ预测 + GS based Embodied Occ
- 也提出了一个benchmark 来做3D occ预测任务
> [!PDF|note] [[EmbodiedOcc.pdf#page=3&selection=75,0,76,55&color=yellow|EmbodiedOcc, p.3]]
> > We maintain an explicit global memory of 3D Gaussians during the exploration of the current scene. 

> [!PDF|note] [[EmbodiedOcc.pdf#page=3&selection=75,0,76,55&color=note|EmbodiedOcc, p.3]]
> > We maintain an explicit global memory of 3D Gaussians during the exploration of the current scene. 

- 估计是先获取一秒的深度预测变成occ
- 从一个H * W *  3的图像输入获取成X * Y * Z * C 的特征， XYZ表示3D坐标系， C表示语义的数量
- 加强
