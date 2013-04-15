Model demo{
	
	
	Header head{
		import "kardelen.phd.printer.*"
		import "kardelen.phd.printer.Engine.*"
		generate Myscheduler
	}
	
	Job Paper{
		RELEASE release_date Integer
		DEMAND Tray
		DEMAND Heater
		DEMAND Fuse
		DEMAND Finisher
		newpath
	}
	
	Executor Tray{
		ACCESS single
	}
	
	Executor Heater{
		ACCESS single
	}
	
	Executor Fuse{
		ACCESS single
	}
	
	Executor Finisher{
		ACCESS single
	}
	

	Resource Power{
		
	}	
	
	
	Scheduler Myscheduler{
		PolicyDefinitions{
			builtin FCFS
			new Userpolicy
			Condition Policychange{
				resource: Power
				FCFS = "Power.getCapacity() > 100";
				Userpolicy = "Power.getCapacity() < 100";
			}
		}
		JobReference{
			Paper
		}
		ResReference{
			Tray
			Heater
			Fuse
			Finisher
		}
		EventReference{
			
		}
		
	}
	
	PathDeclaration newpath{
		Tray->Heater->Fuse->Finisher
	}
	
}EndModel