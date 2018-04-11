## Jarbas Skills Repo

This is my personal skills repository, this is used by JarbasSkillsManager to install new skills

It is basically a personal version of the [official mycroft skills repo](https://github.com/MycroftAI/mycroft-skills)

This is aimed at [jarbas-core](https://github.com/JarbasAl/jarbas-core), but should work just fine in mycroft

## Skills

* core - core skills in every platform
* common - common skills to every platform
* desktop - skills that require desktop platform (assumed to be default platform)
* kde - skills that require kde
* mycroft_mark_1 - skills that require mycroft_mark1
* picroft - skills that require picroft
* jarbas - skills that require jarbas-core

## Adding a skill

create a pull request, add to/create "common_3rd_party.txt" file, alphabetical order please!

    my_skill_name , my_github_url
    
or if you don't provide the url, the official skills repo will be searched for my_skill_name and url extracted from there

    my_skill_name , 
    
if the skill requires a platform add it to "platform_name_3rd_party.txt" instead


## Interacting with this repo

install JarbasSkillsManager

    pip install py_msm
    
do whatever you want

    from py_msm import JarbasSkillsManager

    jsm =JarbasSkillsManager()
    
    # jsm = JarbasSkillsManager(skills_config={"directory":"some/test/path"})
    
    print jsm.platform
    print jsm.default_skills
    print jsm.list_skills()
    print jsm.url_info("https://github.com/JarbasAl/skill-stephen-hawking")
    print jsm.name_info("date time")
    jsm.update_skills()
    jsm.remove_by_name("stephen hawking")
    jsm.install_by_name("diagnostics")
    jsm.install_defaults()
    jsm.set_platform("kde")
    jsm.install_defaults()
