---
layout: distill
title: Spatial Commonsense Graph for Object localisation in Partial Scenes
use_title: true
description: Localising objects in partially observed scenes using Commonsense knowledge and Graph Neural Networks 
note: This work has been accepted at <a href="https://cvpr2022.thecvf.com/">CVPR 2022</a>
date: 2022-03-01
meta_keywords: object localisation, partial scenes, Spatial Commonsense Graph for Object localisation in Partial Scenes, CVPR, Graph Neural Networks
meta_description: Spatial Commonsense Graph for Object localisation in Partial Scenes
importance: 1
category: Research
img: assets/img/SCG/teaser.png 
img_teaser: assets/img/SCG/arch2.png


authors:
  - name: Francesco Giuliari
    url: "https://fgiuliari.github.io/"
    affiliations:
      name: Istituto Italiano di tecnologia (IIT) <br> University of Genoa
  - name: Geri Skenderi
    url: https://geriskenderi.github.io/
    affiliations:
      name: University of Verona
  - name: Marco Cristani
    url: https://profs.sci.univr.it/~cristanm/
    affiliations:
      name: University of Verona
  - name: Yiming Wang
    url: https://www.yimingwang.it/
    affiliations:
      name: Fondazione Bruno Kessler (FBK) <br> Istituto Italiano di tecnologia (IIT)
  - name: Alessio Del Bue
    url: https://www.iit.it/it/people-details/-/people/alessio-delbue
    affiliations:
      name:  Istituto Italiano di tecnologia (IIT)

bibliography: 2018-12-22-distill.bib

# Optionally, you can add a table of contents to your post.
# NOTES:
#   - make sure that TOC names match the actual section names
#     for hyperlinks within the post to work correctly.
#   - we may want to automate TOC generation in the future using
#     jekyll-toc plugin (https://github.com/toshimaru/jekyll-toc).
toc:
  - name: Abstract
    subsections:
      - name: Key Contributions
  - name: Code and Dataset
  - name: Paper
  - name: Examples of localisations
  - name: Contacts

# Below is an example of injecting additional post-specific styles.
# If you use this post as a template, delete this _styles block.

_styles: >
  .fake-img p {
    font-family: monospace;
    color: white;
    text-align: left;
    margin: 12px 0;
    text-align: center;
    font-size: 16px;
  }

  .img_faded{
    opacity: 0.5;
  }

  .carousel_black_bg{
    background-color: rgba(1,1,1,1);
  }

  .carousel{
    height: 500px;
  }
  .carousel-item .{
    height:100%;
  }
  .carousel-item {
    height:100%;
  }
  .carousel-inner{
    height:100%;
  }
  .carousel-inner figure{
    height:100%;
    margin: 0px;
  }

  .carousel-inner figure picture{
    height:100%;
    width:auto;
    max-width:100%;
  }
  .carousel-inner figure picture img{
    height:100%;
    width:auto;
    max-width:100%;
    position:absolute;
    left:0;
    right:0;
    margin: auto;
  }

  a {
    color: #0c77b7 !important; 
  }

---
## Abstract
We solve object localisation in partial scenes, a new problem of estimating the unknown position of an object (e.g. where is the bag?) given a partial 3D scan of a scene. The proposed solution is based on a novel scene graph model, the Spatial Commonsense Graph (SCG), where objects are the nodes and edges define pairwise distances between them, enriched by concept nodes and relationships from a commonsense knowledge base. This allows SCG to better generalise its spatial inference over unknown 3D scenes. The SCG is used to estimate the unknown position of the target object in two steps:
first, we feed the SCG into a novel Proximity Prediction Network, a graph neural network that uses attention to perform distance prediction between the node representing the target object and the nodes representing the observed objects in the SCG; second, we propose a Localisation Module based on circular intersection to estimate the object position using all the predicted pairwise distances in order to be independent of any reference system. We create a new dataset of partially reconstructed scenes to benchmark our method and baselines for object localisation in partial scenes, where our proposed method achieves the best localisation performance.



<div class="row">
<div class="col-1 col-md-2"></div>
    <div class="col-10 col-md-8 ">
        {% include figure.html path="assets/img/SCG/teaser.png" title="Our SCG" class="img-fluid rounded z-depth-0" %}
    </div>
</div>

<div class="row">
<div class="col-0 col-md-1"></div>
    <div class="col-12 col-md-10 ">
<div class="caption">
Given a set of objects (indicated in the green circles) in a partially known scene, we aim at estimating the position of a target object (indicated in the orange circle). We treat this localisation problem as an edge prediction problem by constructing a novel scene graph representation, the Spatial Commonsense Graph (SCG), that contains both the spatial knowledge extracted from the reconstructed scene, i.e. the proximity ( black edges) and the commonsense knowledge represented by a set of relevant concepts (indicated in the pink circles) connected by relationships, e.g. UsedFor ( orange edges) and AtLocation ( blue edges)
</div>
    </div>
</div>
### Key Contributions

**The key contribution of this paper can be summarised as:**
1. We identify a novel task of object localisation in partial scenes and propose a graph-based solution. We make available a new dataset and evaluation protocol, and show that our method achieves the best performance w.r.t. other comparing methods.

2. We propose a new heterogeneous scene graph, the Spatial Commonsense Graph , for an effective integration between the commonsense knowledge and the spatial scene, using attention-based message passing for the graph updates to prioritise the assimilation of knowledge relevant to the task.

3. We propose **SCG Object Localiser**, a two-staged localisation solution that is agnostic to scene coordinates. The distances between the unseen object and all known objects are first estimated and then used for the localisation based on circular intersections.

## Code and Dataset
The dataset is available on gihub:
<div class="row">
    <div class="col-12 col-sm-4">
    <a href="https://github.com/FGiuliari/SpatialCommonsenseGraph-Dataset">
        {% include figure.html path="assets/img/GitHub-Mark.png" title="Dataset" class="img-fluid rounded z-depth-0" %}
    </a>
    <h3 style="text-align:center">Dataset</h3>
    </div>
    <div class="col-sm-4"></div>
    <div class="col-12 col-sm-4">
        {% include figure.html path="assets/img/GitHub-Mark.png" title="Code" class="img-fluid rounded z-depth-0 img_faded" %}
    <h3 style="text-align:center">Code will be available soon.</h3>
    </div>
</div>


## Paper

  The paper will be presented at the Conference on Computer Vision and Pattern Recognition (CVPR 2022)
    
<div class="row">
    <div class="col-12 col-sm-6">
      <a href="/assets/pdf/SCG_site_version.pdf">
          {% include figure.html path="assets/img/SCG/pdf_thumb.png" title="example image" class="img-fluid rounded z-depth-0" %}
      </a>
    </div>
   <div class="col-12 col-sm-6 publications" >

  {% bibliography -f SCG  -T bib_nounderline%}

  </div>
</div>
   

## Examples of localisations
Below You can see some examples of localisation with our proposed approach


<div class="row">
    <div class="col-12">
<div id="carouselExampleIndicators" class="carousel slide" data-ride="carousel">
  <ol class="carousel-indicators">
    <li data-target="#carouselExampleIndicators" data-slide-to="0" class="active"></li>
    <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
    <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
  </ol>
  <div class="carousel-inner">
    <div class="carousel-item active">
        {% include figure.html path="assets/img/SCG/ex_loc1.png" title="example image" class="img-fluid rounded z-depth-0" %}
    </div>
    <div class="carousel-item">
        {% include figure.html path="assets/img/SCG/ex_loc2.png" title="example image" class="img-fluid rounded z-depth-0" %}
    </div>
    <div class="carousel-item">
        {% include figure.html path="assets/img/SCG/ex_loc3.png" title="example image" class="img-fluid rounded z-depth-0" %}
    </div>
  </div>
  <a class="carousel-control-prev" href="#carouselExampleIndicators" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon carousel_black_bg" aria-hidden="true"></span>
    <span class="sr-only">Previous</span>
  </a>
  <a class="carousel-control-next" href="#carouselExampleIndicators" role="button" data-slide="next">
    <span class="carousel-control-next-icon carousel_black_bg" aria-hidden="true"></span>
    <span class="sr-only">Next</span>
  </a>
</div>
</div>
</div>


## Contacts

For any question you can open an issue on [GitHub](https://github.com/FGiuliari/SpatialCommonsenseGraph-Dataset/issues) or send an email to [Francesco Giuliari](mailto:francesco.giuliari@iit.it).