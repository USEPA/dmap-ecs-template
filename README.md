# dmap-ecs-template


You can clone this repo but in order to run the workflow actions the DMAP admins will need to coordinate a few things prior to the workflow operating.
1. The DMAP admins will need to know the name of the connecting repo. 
2. The Repo will need to be comming from the USEPA GitHub Organization. 
3. An AWS IAM Role will need to be created the DMAP admins.  This will need to be cordinated so that the appropriate IAM actions are allowed.
4. The cloned Repo will need to have change the .github/workflows/main.yml file to map to the newly created role.  Example below:

      - name: Configure AWS credentials
        uses: aws-actions/configure-aws-credentials@v2
        with:
          role-to-assume: arn:aws:iam::xxxxxxxxxxxxxxxxx:role/github_usepa_actions_role
          aws-region: us-east-1

This example assumes an ECR repo exists and the main.yml file will need to reflect the name of the ECR repo.  
