# Wordpress-breadcrumbs
Create custom wordpress breadcrumbs based on url slug

 function getproductname(){	
	 /* Grab the link. */
     $link = $_SERVER['REQUEST_URI'];
     $parts = explode("/", $link);
     $value = $parts[2];
	 //print_r($value);

$page = get_page_by_path( $value );
//echo get_the_title( $page );

			
	echo '<ul class="ha-breadcrumbs">
	        <li class="ha-breadcrumbs-item ha-breadcrumbs-start">
			    <a href="https://www.persianandmodernrugs.com/" rel="home"><span class="ha-breadcrumbs-text">Home</span>
				</a>
			</li>
			<li class="ha-breadcrumbs-separator"><span class="ha-breadcrumbs-separator-icon">
			   <i class="fas fa-angle-right" aria-hidden="true"></i></span>
			</li>
			<li class="ha-breadcrumbs-item">
			   	<a href="https://www.persianandmodernrugs.com/modern-rugs/"><span class="ha-breadcrumbs-text">Modern rugs</span></a>
			</li>
			<li class="ha-breadcrumbs-separator"><span class="ha-breadcrumbs-separator-icon">
				<i class="fas fa-angle-right" aria-hidden="true"></i></span>
			</li>
			<li class="ha-breadcrumbs-item ha-breadcrumbs-end">
				<span class="ha-breadcrumbs-text">'.get_the_title( $page ).'</span>
			</li>
		</ul>';
}

add_shortcode('showproductname','getproductname');
