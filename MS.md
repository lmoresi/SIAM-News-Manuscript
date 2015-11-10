## Computational Plate Tectonics and the Geological Record in the Continents

Earth Scientists recently celebrated the fifty year anniversary of the theory of Plate Tectonics. The notion that the Earth's surface is composed of a small number of slowly, but continually, moving 'rigid' plates floating on a convecting, fluid interior is now firmly established as the foundation concept of the discipline. Thanks to space geodesy, those motions are now routinely observable and I have illustrated them in the map in Figure 1. In that map, I have also plotted the second invariant of the strain-rate which is clearly vanishingly small in the plate interiors and large at the plate boundaries.

If the plates can be considered rigid then they are merely boundary conditions on a global circulation problem.  The theory of plate tectonics is actually a kinematic description of plate motions that tells is how the plates move but it does not tell us why they move as they do. It does not explain how and why new boundaries form or what happens in the continental regions where deformation is more diffuse. We do not know how or when plate tectonics started, or why we only see plate motions on Earth and not on other planets or moons in the solar system. To address these questions requires a fully dynamic theory of plate motion and constitutive behaviour.

![**Figure 1:** The surface of the Earth is continually moving in response to convection currents in the underlying mantle. A map of the surface velocities shows the motions are organised into a strikingly simple pattern of surface "plates" that are almost rigid bodies. The surface strain rate - coloured contours - is concentrated at the plate boundaries. On closer inspection, there are many regions within the continental crust where the motions are diffuse, not at all plate-like. The arrows are colored by their angle to North as a means of distinguishing the different plates. The scale is such that the longest vector represents 10cm/yr.](Figures/StrainRatePlateMotions.png)

 In Figure 1, I have deliberately chosen contours of the strain rate to show that there are some regions where the plate boundaries are relatively diffuse (which is the same thing as saying that there are places where the plates are not rigid). Many of these occur in the continents - particularly obvious is the regional deformation associated with the collision of India and Eurasia which produces the Himalayan mountain belt. The realization that the plates are not rigid is the first step towards one of the most enduring and significant challenge facing the Earth Sciences, namely, a coupled model of deep circulation, plate motions and continental deformation.

There are two reasons why a global circulation model for the solid Earth is a grand challenge problem. The first is that rheology is very non-linear and history dependent (see ["Modelling Large Scale Flow"](#modelinglarge-scaleflow) below) because it represents processes which occur at a much smaller temporal and spatial scale than the plates. Such processes include the mechanics of formation and slip on faults through the accumulated effect of thousands of small earthquakes (see Figure 2), and the effects of grain-scale deformation and melting of the minerals from which the rocks are constituted.  

![**Figure 2** - One of the most dramatic departures from plate-like deformation on Earth occurs where the Indian subcontinent collides with the Eurasian continent. The map on the left is a satellite image with the flow lines from the plate motion vector field from Figure 1 drawn in red. The major rivers which drain the Himalayan mountain belt and the plateau are also shown. On the right is the same region showing 50 years of Earthquake data for events larger than magnitude 4.5, colored by depth and superimposed on the strain rate](Figures/Himalaya.png)

The second aspect of the grand challenge is how we go about finding and using observations which can constrain the many additional degrees of freedom that large-scale, dynamic circulation models require. To appreciate the scale of this challenge requires a recognition of the fundamental difference between the geological record of the ocean floor (the plates) and the geological record of the continental crust. The oceanic crust is actually part of the three-dimensional, deep circulation pattern of the solid Earth. The overturn time of this circulation is of the order of 100 million years and this is comparable to the median age of the oceanic plates. The continental crust is buoyant enough to escape large-scale recycling and is much more widely distributed in age (ranging up to 3+ billion years). The continental record may be longer, but it is an indirect record.

![**Figure 3** - A low-angle view of a numerical model of continental collision using the Underworld particle-in-cell finite element code. The map (1) shows the how to interpret the model in terms of the India-Eurasia collision. In the movie, the (Indian) indentor heads towards the viewer and crumples the crust into a mountain belt in the foreground. In the background, the crust escapes away from the viewer pulled by the subduction zone in the background. Snapshots from the movie: (2), pre-collision and (3), late in the collision. [MOVIE](https://www.dropbox.com/s/52yrz5ttxylk2rw/Orocline.mov?dl=0)](Figures/OrogenCollider.png)

Consider, for example, the Himalayan mountain belt. This is the result of the congestion of a subduction zone by the buoyant and deformable continental crust. The rocks record the history of that collision in the crumpled and overturned units. The deformation also results in the dramatic topography of the region as the crust is shortened and thickened (See Figure 3 and the accompanying movie). The history of the uplifted surface can be inferred by examining the stratigraphy, cooling history, and metamorphism of the rocks. It is also indirectly recorded in the sedimentary record as rivers and glaciers carry material away from the mountain belts and into sedimentary basins.

Sedimentary basins are to geologists what rubbish tips are to archeologists: places where the accumulated detritus of an age is safely stashed away, roughly in order from youngest at the top to oldest at the bottom. The difficulty in inverting such a signal to tell us about the history of geological deformation is that the transport of eroded sediment can occur over long distances, is very dependent on the history of the topography, can be very variable in time and space, is sensitive to very small-scale processes and is coupled to the large scale deformation. This is immediately obvious looking at a map of the major rivers which drain the himalayas (Figure 2). The lengthy, tortuous pathways they often take to reach the ocean are very obviously influenced by changes to the topography occurring as the streams and rivers cut their channels. For discussion of the computational and mathematical challenges in coupling global circulation models of the solid Earth with the erosion, transport and deposition of sediment, see ["Coupling to Sediment Transport Models"](#couplingtosedimenttransportmodels) below.

### Discussion

Global circulation models for the solid Earth are needed to bring the power of plate tectonic theory to the continental geological record. However, to make these models meaningful, they will have to embed models which can reproduce observable aspects of that continental record. That this is a grand challenge problem is amply illustrated by considering just one of those observables: the effect of weather at the surface in driving erosion and transport of sediment.
### Modeling Large-Scale Flow

To model the flow in the mantle and the response of the plates, we need to solve a simplified system of equations. A typical template for this problems reduces to the Stokes equation for an incompressible fluid (or nearly so) driven by thermal buoyancy due to planetary cooling and deep radioactive decay\(( \mathrm{.} \))

<!-- Need some math mode stuff before these equations will be detected -->
\begin{equation}
    \nabla \cdot \boldsymbol{\tau} - \nabla p  = g \rho  \hat{z}
    \label{eq:stokes}
\end{equation}

\begin{equation}
    \nabla \cdot \mathbf{u}   = 0
    \label{eq:incomp}
\end{equation}

\begin{equation}
    \frac{D T}{D t} = \nabla( \kappa \nabla T ) + Q
    \label{eq:advdiff}
\end{equation}

Silicate rocks deform as an extremely high viscosity fluid over geological time and this eliminates the need to consider the effects of inertia and rotation. However, this is the last of the good news, a significant complexity arises from the rheology which is strongly dependent on deformation history and composition.

\begin{equation}
    \frac{{\tau} _ {ij}}{\eta} +
    \color{Red}{\frac{\dot{\tau} _ {ij} }{\mu}} +
    \color{Blue}{ \Lambda _ {ijkl} \tau _ {kl} }  =
     \frac{\partial u _ i}{\partial x _ j} + \frac{\partial u _ i}{\partial x _ j}
     \label{eq:constitutive}
\end{equation}

The second term in the constitutive law (in red) is the effect of viscoelasticity and the third term represents the effects of faulting and other forms of material failure as a non-isotropic and strain-dependent plasticity. At the large length and time scale of these models, it is common to neglect elastic stresses, but the plate boundaries are represented through the plasticity term and these are central to the formulation.

The most successful algorithms for dealing with the elliptic Stokes equation and the history-dependent rheology are hybrids with an Eulerian mesh suitable to build an efficient, parallel, multigrid solver for (\(( \ref{eq:stokes} \))) and Lagrangian particles embedded in the fluid which record the stress and strain history required for (\((\ref{eq:constitutive}\))). In the `Underworld` code (REF), the particle properties map to the mesh via a finite element quadrature rule that has to be constructed on-the-fly for the distribution of particles found in each element at every timestep.   


### Coupling to Sediment Transport Models

![**Figure 4** - Idealised erosion, transport and deposition models are based on computing height changes which depend on local slope, those dependent on long-range transport processes by rivers or glaciers, and motions due to large-scale tectonics. Long-range transport by rivers requires us to know information integrated from the entire upstream catchment of every point. Erosion tends to localise, whereas deposition has the opposite characteristic (1, 2). Upstream integrals can be calculated very efficiently with an appropriately ordered traversal of the graph of downhill-connectivity of the surface (3, 4). Parallel algorithms based on arbitrary spatial decompositions of the domain disrupt this efficient ordering.](Figures/SurfaceProcess.png)


\begin{equation}
    \frac{D h}{D t} =
    \color{Red} { \nabla\left( \kappa(h) \nabla h \right) } -
    \color{Blue}{ K A ^ m \left| h \right| ^n + \dot  h_\mathrm{basement} }
    \label{eq:surfaceprocess}
\end{equation}

\begin{equation}
    A = \\! \\! \\! \\! \int \limits _ { \xi, \mathrm{upstream}} \\!\\!\\!\\! \alpha ( \xi )
    \label{eq:upstream}
\end{equation}

We can limit the discussion of erosion, sediment transport and deposition to those that are most likely to be important at scales of hundreds of km and hundreds of thousands to millions of years. We can consider the changing height of a simple surface described by \(( h(x(t),y(t)) \)) with the simplified description outlined in equation (\(( \ref{eq:surfaceprocess}\))). The time derivative of the surface height is computed as a balance between local, non-linear, diffusion-like terms (red) and non-local terms related to the integrated upstream area for any point (\((\ref{eq:upstream}\))). Such terms occurs because, for example, the available energy of a river in eroding the basement is expected to relate to both the local slope and the total amount of water in the river. To know how much sediment a river is carrying, the net erosion rate upstream needs to be known for every point along the river. Figure 4 illustrates the network that can be constructed from downhill flow pathway for a discrete set of points representing the surface and how integrating (\(( \ref{eq:surfaceprocess}\))) produces a tree-like collection of pathways which cut into the surface. Such pathways form narrow, localised channels that can be very stable. However, where deposition occurs (when the energy of the flow decreases in a flatter region, for example) then the reverse is true: flows tend to diverge, multiple pathways across low-relief surfaces develop. It is much harder to apply the ordered traversal of a tree that is diverging in this way. A promising approach in this case, which is also efficient for domain-decomposed parallel computation, is to use repeated applications of the adjacency matrix of the downhill-directed graph corresponding to the flow network. Such approaches are needed when the surface is not modelled in isolation but as part of a large computation such as the one shown in Figure 3.

---


### Acknowledgements, Further Reading and References

The maps were produced using the `cartopy` plotting package (REF) with data from the following sources: Global topography and bathymetry from ETOPO1 ( REF ), Plate motions and strain rates from the global strain rate project (REF), Satellite images from Mapbox (REF url), Seismic data from the IRIS catalog (REF)


Strain rate data that I used:

Kreemer, C., W.E. Holt, and A.J. Haines, An integrated global model of present-day plate motions and plate boundary deformation, Geophys. J. Int., 154, 8-34, 2003.
