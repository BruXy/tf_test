.PHONY: init plan apply destroy graph clean

init:
	terraform init

apply: init
	terraform apply

plan: init
	terraform plan

destroy: init
	terraform destroy

graph:
	environment=$$(sed -ne '/environment/{s/.*"\([^"]*\)"/\1/p}' terraform.tfvars); \
		terraform graph -draw-cycles -type=plan | dot -Tsvg > $${environment}.svg

clean:
	rm -rf .terraform


