# SimpleNavigationAppKotlin

1- Add the dependencies for the artifacts you need in the build.gradle file for your app or module:
dependencies {
  val nav_version = "2.7.4"
  .
  .
  .
  // Kotlin
  implementation("androidx.navigation:navigation-fragment-ktx:$nav_version")
  implementation("androidx.navigation:navigation-ui-ktx:$nav_version")
  .
  .
  .
}


2-To add Safe Args to your project, Add a buildscript group to the top of the build.gradle(Project) file.
buildscript {
    dependencies {
        classpath("androidx.navigation.safeargs:androidx.navigation.safeargs.gradle.plugin:2.4.1")
    }
}

Then add the plugin ID to the plugins group in the build.gradle(Module) file.
id ("androidx.navigation.safeargs")

Make sure the line android.useAndroidX=true is in gradle.properties.

3-Add viewBinding on Fragment
Add this in build.gradle(Module:app) and then sync
buildFeatures{
        viewBinding = true 
    }

declaration : private lateinit var binding: FragmentFirstBinding
initialize :  
    override fun onCreateView(
        inflater: LayoutInflater, container: ViewGroup?,
        savedInstanceState: Bundle?
    ): View? {
        // Inflate the layout for this fragment
        binding = FragmentFirstBinding.inflate(inflater,container,false)
        return binding.root
    }
