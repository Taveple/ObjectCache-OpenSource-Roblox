# ObjectCache-OpenSource-Roblox

-- Created by Taveple 11/12/2022
-- Updated 08/04/2023

--[[

	This module aims to solve the issue of needing large amount of parts to be spawned in at once by pre-creating them
	and making it easier to be pulled and used when needed. I have compiled as many methods as I could think of,
	let me know if you can think of any more or find any bugs and message me on devforum. 
	
	!!
		Models are not recommended for object caching as they can contain many parts. However, I have still 
		provided support for it.
	!!
	
	
	vv All Functions vv
	
	
	- Setup -
	
	
	- This function creates a new cache of objects to be used, the main function in this module. It also returns the data key for the Cache.
		CreateCache(CacheName: string, TemplateObject: Instance, StartAmount, RegistryAmount: number, NameObjectsInNumericalOrder: boolean): table
	
	- This function will remove any cache you create using CreateCache.
		RemoveCache(CacheName: string, CacheKey: table)
	
	- This function will remove all caches created.
		CleanupAllCaches()
	
	
	- Usage - 
	
	
	- This function will get a random or specific object from the list of cached objects. If the cache is running lower than the registry amount, it will generate more objects.
		GetObject(CacheName: string): Instance
	
	- This function will cache the object that was pulled out of the cache list.
		CacheObject(CacheName: string, InstanceObject: Instance)
	
	- This function will cache all objects.
		CacheAllObjects(CacheName: string)
	
	- This function will generate more objects based on the registry amount set.
		NewRegistry(CacheName: string)
	
	- This function will remove a specific amount of random objects from the cache.
		RemoveFromCache(CacheName: string, Amount: number)
]]

