## Computational Plate Tectonics and the Geological Record in the Continents

Earth scientists recently celebrated the fifty-year anniversary of the theory of plate tectonics. The notion that the Earth’s surface is composed of a small number of slowly but continually-moving ‘rigid’ plates floating on a convecting, fluid interior is now firmly established as the foundational concept of the discipline, and, in the last decade, have become routinely observable thanks to space geodesy, as seen in Figure 1.

If the plates can be considered rigid, then they are merely boundary conditions on a global circulation problem. The theory of plate tectonics is actually a kinematic description of plate motion that describes how the plates move, but it does not tell us why they move as they do. Neither does it explain how and why new boundaries form or show what happens in the continental regions where deformation is more diffuse. We don’t know how or when plate tectonics began, or why plate motions are only observed on Earth and not on other planets or moons in the solar system. Addressing these questions requires a fully-dynamic theory of plate motion and constitutive behaviour.

![A map of  surface velocities shows that the surface motions are organised into a strikingly simple pattern of surface “plates” that are almost rigid bodies. The surface strain rate–coloured contours—is concentrated at the plate boundaries. The map also displays the second invariant of the strain-rate, which is vanishingly small in the plate interiors and large at the plate boundaries. The arrows are colored by their angle to ‘North’ as a means of distinguishing the different plates. The scale is such that the longest vector represents 10cm/yr. ](Figures/StrainRatePlateMotions.png)

**Figure 1.** *A map of  surface velocities shows that the surface motions are organised into a strikingly simple pattern of surface “plates” that are almost rigid bodies. The surface strain rate–coloured contours—is concentrated at the plate boundaries. The map also displays the second invariant of the strain-rate, which is vanishingly small in the plate interiors and large at the plate boundaries. The arrows are colored by their angle to ‘North’ as a means of distinguishing the different plates. The scale is such that the longest vector represents 10cm/yr.*

The contours of the strain rate in Figure 1 show some regions where plate boundaries are relatively diffuse,  (meaning that the plates are not rigid there). Most of these regions occur in the continents - particularly obvious is the regional deformation associated with the collision of India and Eurasia which produces the Himalayan mountain belt. The realization that the plates are not rigid is the first step towards addressing one of the most enduring and significant challenges facing the Earth sciences: the development of a coupled model of deep circulation, plate motions, and continental deformation.

Developing a global circulation model for the solid Earth is a grand challenge problem. Rock rheology, the manner in which rocks deform under tectonic stress, is very non-linear and history-dependent because it represents processes that occur at a much smaller temporal and spatial scale than plate motions. Such processes include the mechanics of faults formation and the manner in which they slip via the accumulated effect of thousands of small earthquakes (see Figure 2), combined with the effects of grain-scale deformation, metamorphism and melting.

![One of the most dramatic departures from plate-like deformation on Earth occurs where the Indian subcontinent is colliding with the Eurasian continent. The map on the left is a satellite image with the flow lines from the plate motion vector field drawn in red. On the right is the same region showing 50 years of earthquake data for events larger than magnitude 4.5, colored by depth and superimposed on the strain rate.](Figures/Himalaya.png)

**Figure 2.** *One of the most dramatic departures from plate-like deformation on Earth occurs where the Indian subcontinent is colliding with the Eurasian continent. The map on the left is a satellite image with the flow lines from the plate motion vector field drawn in red. On the right is the same region showing 50 years of earthquake data for events larger than magnitude 4.5, colored by depth and superimposed on the strain rate.*

Another aspect of the grand challenge is determining how to find and use observations which can constrain the many additional degrees of freedom required by large-scale, dynamic circulation models. Appreciating the scale of this challenge requires recognition of the fundamental difference between the geological record of the ocean floor (the plates) and the geological record of the continental crust. The oceanic crust is part of the three-dimensional, deep circulation pattern of the solid Earth, with an overturn time r of around 100 million years,  comparable to the median age of the oceanic plates. The continental crust is buoyant enough to escape large-scale recycling and much more widely-distributed in age (ranging up to over three billion years).

![A low-angle view of a numerical model of continental collision using the Underworld particle-in-cell finite element code. The map (1) interprets the model in terms of the India-Eurasia collision. In the simulation, the Indian indentor heads towards the viewer and crumples the crust into a mountain belt in the foreground. In the background, the crust escapes away from the viewer pulled by the subduction zone. Snapshots from the movie: (2) pre-collision and (3) late in the collision](Figures/OrogenCollider.png)

**Figure 3.** *A low-angle view of a numerical model of continental collision using the Underworld particle-in-cell finite element code. The map (1) interprets the model in terms of the India-Eurasia collision. In the simulation, the Indian indentor heads towards the viewer and crumples the crust into a mountain belt in the foreground. In the background, the crust escapes away from the viewer pulled by the subduction zone. Snapshots from the movie: (2) pre-collision and (3) late in the collision*

Consider the Himalayan mountain belt, which is the result of subduction zone congestion by the buoyant and deformable continental crust. The continental collision results in the dramatic topography of the region as the crust is shortened and thickened (Sse Figure 3, and  view an accompanying movie at sinews.siam.org). Examining the stratigraphy, cooling history, and metamorphism of the rocks allows one to infer the history of the uplifted surface, which is recorded by rocks in crumpled and overturned units. It is also indirectly recorded in the sedimentary record as rivers and glaciers carry material away from the mountain belts and into sedimentary basins.

In sedimentary basins, accumulated detritus from the landscape stacks up, burying older material and creating a stratigraphic record of the topographic erosion. The difficulty in inverting this record to reveal the history of geological deformation is that the transport of eroded sediment can occur over long distances, is very dependent on the history of the topography, can be quite variable in time and space, is sensitive to very small-scale processes, and is coupled to the large-scale deformation. For example, the lengthy, tortuous pathways that the major rivers draining the Himalayas have to take to reach the ocean are clearly influenced by the topography rising and translating beneath the streams and rivers as they cut their channels.

<hr>
**Material below should be deleted in print version**
<hr>

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

Silicate rocks deform in the same way an extremely high-viscosity fluid on geological timescales, which eliminates the need to consider the effects of inertia and rotation. However, a significant complexity arises from the rheology, which is strongly dependent on deformation history and composition.

\begin{equation}
    \frac{{\tau} _ {ij}}{\eta} +
    \color{Red}{\frac{\dot{\tau} _ {ij} }{\mu}} +
    \color{Blue}{ \Lambda _ {ijkl} \tau _ {kl} }  =
     \frac{\partial u _ i}{\partial x _ j} + \frac{\partial u _ j}{\partial x _ i}
     \label{eq:constitutive}
\end{equation}

The second term in the constitutive law (\((\ref{eq:constitutive}\))) (in red) is the effect of viscoelasticity, and the third term represents the effects of faulting and other forms of material failure as a non-isotropic and strain-dependent plasticity. Neglecting elastic stresses is common at the large length and time scale of these models, but plate boundaries are represented through the plasticity term and these are central to the formulation.

The most successful algorithms for dealing with the elliptic Stokes equation and the history-dependent rheology are hybrids with an Eulerian mesh suitable to build an efficient, parallel, multigrid solver for (\(( \ref{eq:stokes} \))) and Lagrangian particles embedded in the fluid which record the stress and strain history required for (\((\ref{eq:constitutive}\))). In the  Underworld code (Moresi et al, 2007), the particle properties map to the mesh via a finite element quadrature rule that must be constructed on-the-fly for the distribution of particles found in each element at every timestep.

![Idealised erosion, transport and deposition models are based on computing height changes which depend on local slope, those dependent on long-range transport processes by rivers or glaciers, and motions due to large-scale tectonics. Long-range transport by rivers requires us to know information integrated from the entire upstream catchment of every point. Erosion tends to localise, whereas deposition has the opposite characteristic (1, 2). Upstream integrals can be calculated very efficiently with an appropriately ordered traversal of the graph of downhill-connectivity of the surface (3, 4). Parallel algorithms based on arbitrary spatial decompositions of the domain disrupt this efficient ordering.](Figures/SurfaceProcess.png)

**Figure 4.** *Idealised erosion, transport and deposition models are based on computing height changes which depend on local slope, those dependent on long-range transport processes by rivers or glaciers, and motions due to large-scale tectonics. Long-range transport by rivers requires us to know information integrated from the entire upstream catchment of every point. Erosion tends to localise, whereas deposition has the opposite characteristic (1, 2). Upstream integrals can be calculated very efficiently with an appropriately ordered traversal of the graph of downhill-connectivity of the surface (3, 4). Parallel algorithms based on arbitrary spatial decompositions of the domain disrupt this efficient ordering.*

$$ $$
\begin{equation}
    \frac{D h}{D t} =
    \color{Red} { \nabla\left( \kappa(h) \nabla h \right) } -
    \color{Blue}{ K A ^ m \left| h \right| ^n } +
    \dot  h _ \mathrm{basement}
    \label{eq:surfaceprocess}
\end{equation}

$$ $$
\begin{equation}
    A = \\! \\! \\! \\! \int \limits _ { \xi, \mathrm{upstream}} \\!\\!\\!\\! \alpha ( \xi ) d\xi
    \label{eq:upstream}
\end{equation}

It is only necessary to consider those processes contributing to erosion, sediment transport and deposition that are important at scales of hundreds of km and hundreds of thousands to millions of years. Consider the changing height of a simple surface described by \(( h(x(t),y(t)) \)) with the simplified description outlined in equation (\(( \ref{eq:surfaceprocess}\))). The time derivative of the surface height is computed as a balance between local, non-linear, diffusion-like terms (red) and non-local terms related to the integrated upstream area for any point (\((\ref{eq:upstream}\))). Such terms occurs because, for example, the available energy of a river in eroding the basement is expected to relate to both the local slope and the total amount of water in the river. To know how much sediment a river is carrying, the net erosion rate upstream needs to be known for every point along the river. Figure 4 illustrates the network that can be constructed from downhill flow pathway for a discrete set of points representing the surface and how integrating (\(( \ref{eq:surfaceprocess}\))) produces a tree-like collection of pathways which cut into the surface. Such pathways form narrow, localised channels that can be very stable. However, where deposition occurs (when the energy of the flow decreases in a flatter region, for example) then the reverse is true: flows tend to diverge, multiple pathways across low-relief surfaces develop. It is much harder to apply the ordered traversal of a tree that is diverging in this way. A promising approach in this case, which is also efficient for domain-decomposed parallel computation, is to use repeated applications of the adjacency matrix of the downhill-directed graph corresponding to the flow network. Such approaches are needed when the surface is not modelled in isolation but as part of a large computation such as the one shown in Figure 3.


Solving a simplified system of equations is necessary to model the flow in the mantle and the plates’ response. A typical template for this problem uses the Stokes equation for an incompressible fluid (or nearly so) driven by thermal buoyancy due to planetary cooling and deep radioactive decay:

For details of the computational and mathematical models described in this article, together with references and background reading, please see the full version of this article at sinews.siam.org.

### Acknowledgements

The maps were produced using the *cartopy* plotting package (Met Office, 2010) with data from the following sources: Global topography and bathymetry from ETOPO1 (Amante & Eakins, 2009), Plate motions and strain rates from the global strain rate project (Kreemer et al, 2003), Satellite images from Mapbox (mapbox.com), Seismic data were obtained using the *obspy* package (Beyreuther et al, 2010).

### Further Reading

Many of the papers which first described the theory of plate tectonics are extremely accessible. Wilson's 1963 paper on continental drift and Heirtzler's 1968 paper on sea-floor spreading bracket the period of the major discoveries.

Moresi et al, (2000) is a review of computational plate tectonics written for a broad audience which describes the methods discussed here with examples. Stadler et al (2010) talk about applications of adaptive mesh refinement to a solid Earth global circulation model with emergent plate boundaries. More background on Figure 3 and the movie can be found in Moresi et al, (2014).

To learn more about the large-scale interaction between mantle circulation and the surface processes of erosion, sediment transport and deposition, see the review paper by Braun (2010).

### References

Amante, C. and B.W. Eakins, 2009. ETOPO1 1 Arc-Minute Global Relief Model: Procedures, Data Sources and Analysis. NOAA Technical Memorandum NESDIS NGDC-24. National Geophysical Data Center, NOAA. doi:10.7289/V5C8276M ( accessed - 2015.10.30 ).

Beyreuther, M., R. Barsch, L. Krischer, T. Megies, Y. Behr, and J. Wassermann (2010), ObsPy: A Python Toolbox for Seismology, Seismological Research Letters, 81(3), 530–533, doi:10.1785/gssrl.81.3.530.

Braun, J. (2010), The many surface expressions of mantle dynamics, Nature Geoscience, 3(12), 825–833, doi:10.1038/ngeo1020.

Heirtzler, J. R. (1968), Sea-Floor Spreading, Scientific American, ?, 60–70.

Kreemer, C., W. E. Holt, and A. J. Haines (2003), An integrated global model of present-day plate motions and plate boundary deformation, Geophysical Journal International, 154, 8–34.

Met Office (2010), Cartopy: a cartographic python library with a matplotlib interface, Exeter, Devon.

Moresi, L. N., M. Gurnis, S. Zhong, and S. J. Zhong (2000), Plate tectonics and convection in the Earth's mantle: Toward a numerical simulation, Computing in Science & Engineering

Moresi, L. N., S. Quenette, V. Lemiale, C. Mériaux, B. Appelbe, and H. B. Muhlhaus (2007), Computational approaches to studying non-linear dynamics of the crust and mantle, Physics of the Earth and Planetary Interiors, 163(1-4), 69–82, doi:10.1016/j.pepi.2007.06.009.

Moresi, L. N., P. G. Betts, M. S. Miller, and R. A. Cayley (2014), Dynamics of continental accretion, Nature, 508(7495), 245–248, doi:10.1038/nature13033.

Stadler, G., M. Gurnis, C. Burstedde, L. C. Wilcox, L. Alisic, and O. Ghattas (2010), The Dynamics of Plate Tectonics and Mantle Flow: From Local to Global Scales, Science, 329(5995), 1033–1038.

Wilson, J. T. (1963), Continental drift, Scientific American, 208(4), 86–100.
