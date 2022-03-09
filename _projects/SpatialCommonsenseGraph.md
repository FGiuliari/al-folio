---
layout: distill
title: Spatial Commonsense Graph for Object localisation in Partial Scenes
description: Localising objects in partially observed scenes using Commonsense knowledge and Graph Neural Networks <br><br> <b>This work has been accepted at CVPR 2022</b>
date: 2022-03-01
meta_keywords: object localisation, partial scenes, Spatial Commonsense Graph for Object localisation in Partial Scenes
meta_description: Spatial Commonsense Graph for Object localisation in Partial Scenes

years: [2021, 2020, 2018 ]


authors:
  - name: Francesco Giuliari
    url: "https://fgiuliari.github.io/"
    affiliations:
      name: Italian Institute of Technology (IIT) <br> University of Genoa
  - name: Geri Skenderi
    affiliations:
      name: University of Verona
  - name: Marco Cristani
    affiliations:
      name: University of Verona
  - name: Yiming Wang
    url: https://www.yimingwang.it/
    affiliations:
      name: Bruno Kessler Foundation (FBK) <br> Italian Institute of Technology, Italy
  - name: Alessio Del Bue
    affiliations:
      name:  Italian Institute of Technology

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

---


## Abstract
We solve object localisation in partial scenes, a new problem of estimating the unknown position of an object (e.g. where is the bag?) given a partial 3D scan of a scene. The proposed solution is based on a novel scene graph model, the Spatial Commonsense Graph (SCG), where objects are the nodes and edges define pairwise distances between them, enriched by concept nodes and relationships from a commonsense knowledge base. This allows SCG to better generalise its spatial inference over unknown 3D scenes. The SCG is used to estimate the unknown position of the target object in two steps:
first, we feed the SCG into a novel Proximity Prediction Network, a graph neural network that uses attention to perform distance prediction between the node representing the target object and the nodes representing the observed objects in the SCG; second, we propose a Localisation Module based on circular intersection to estimate the object position using all the predicted pairwise distances in order to be independent of any reference system. We create a new dataset of partially reconstructed scenes to benchmark our method and baselines for object localisation in partial scenes, where our proposed method achieves the best localisation performance.



<div class="row">
    <div class="col-12">
        {% include figure.html path="assets/img/SCG/teaser.png" title="example image" class="img-fluid rounded z-depth-0" %}
    </div>
</div>
<div class="caption">
Given a set of objects (indicated in the green circles) in a partially known scene, we aim at estimating the position of a target object (indicated in the orange circle). We treat this localisation problem as an edge prediction problem by constructing a novel scene graph representation, the Spatial Commonsense Graph (SCG), that contains both the spatial knowledge extracted from the reconstructed scene, i.e. the proximity ( black edges) and the commonsense knowledge represented by a set of relevant concepts (indicated in the pink circles) connected by relationships, e.g. UsedFor ( orange edges) and AtLocation ( blue edges)
</div>

### Key Contributions

**The key contribution of this paper can be summarised as:**
1. We identify a novel task of object localisation in partial scenes and propose a graph-based solution. We make available a new dataset and evaluation protocol, and show that our method achieves the best performance w.r.t. other comparing methods.

2. We propose a new heterogeneous scene graph, the Spatial Commonsense Graph , for an effective integration between the commonsense knowledge and the spatial scene, using attention-based message passing for the graph updates to prioritise the assimilation of knowledge relevant to the task.

3. We propose **SCG Object Localiser**, a two-staged localisation solution that is agnostic to scene coordinates. The distances between the unseen object and all known objects are first estimated and then used for the localisation based on circular intersections.

## Code and Dataset
The dataset and code for he paper can be found in this repo:
<div class="row">
    <div class="col-6 col-sm-3">
    <a href="https://github.com/FGiuliari/SpatialCommonsenseGraph-Dataset">
        {% include figure.html path="assets/img/GitHub-Mark.png" title="example image" class="img-fluid rounded z-depth-0" %}
    </a>
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
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="sr-only">Previous</span>
  </a>
  <a class="carousel-control-next" href="#carouselExampleIndicators" role="button" data-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="sr-only">Next</span>
  </a>
</div>
</div>
</div>